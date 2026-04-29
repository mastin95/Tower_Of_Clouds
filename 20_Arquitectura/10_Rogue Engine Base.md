---
type: architecture
status: reverse-documented
tags: [arquitectura]
updated: 2026-04-24
source: Assets/RogueEngine/ (Unity project at C:\Users\Usuario\Documents\UnityProjects\Card_Rehersal)
date: 2026-03-23
---

# RogueEngine — Base Architecture Reference

> **Note**: This document was reverse-engineered from the existing RogueEngine asset.
> It captures the current implementation as a foundation reference. Creative direction
> and game-specific design decisions are documented separately in [[11_Concepto del Juego]]
> and [[12_Mecánicas Centrales]].

## Overview

RogueEngine is a data-driven roguelike deckbuilder framework for Unity. It provides
a complete card game pipeline: battle logic, card effects, AI, map progression, UI,
and save system. The project ("Card Rehearsal" — working title) is built by heavily
modifying this asset.

**Engine**: Unity 6.3 LTS (6000.3)
**Language**: C#
**Key Plugins**: Odin Inspector (Sirenix)
**Architecture Style**: ScriptableObject-driven with event bus

---

## Core Architecture

```
GameManager (singleton facade)
├── BattleLogic    — Turn resolution, card/character management
├── WorldLogic     — Map progression, events, run state
├── World          — Persistent game state (serializable)
└── AIPlayer       — Enemy AI controller
```

### Event System (Dual-Bus)

- **UnityActions** on BattleLogic — direct subscriptions
- **GameEvents** — static event bus for decoupled listeners (UI, FX)

### Data Pipeline

All game content is defined as **ScriptableObjects** loaded via `Resources.Load<T>()`.
DataLoader initializes all registries at startup.

---

## System Inventory

### 1. Card System

| Component | Description |
|-----------|-------------|
| **CardData** | ScriptableObject: id, title, art, mana cost, type (Skill/Power), item type, rarity, team, traits, abilities |
| **Card** (runtime) | Instance with uid, level, mana modifiers, status effects, cached ability references |
| **AbilityData** | Trigger → Target → Conditions → Filters → Effects chain |
| **Card Types** | Skill (play & discard), Power (play & stays on board) |
| **Item Types** | Quest, Consumable, Card (added to deck), Passive (always-on) |

**Asset count**: 225 cards, 272 abilities

### 2. Ability Resolution Pipeline

```
Trigger fires (OnPlay, StartOfTurn, OnDeath, etc.)
  → Check trigger conditions (on caster)
  → Resolve targeting (AbilityTarget enum)
  → Check target conditions (on each target)
  → Apply filters (Random, First, HighestStat, LowestStat)
  → Execute effects (polymorphic DoEffect calls)
  → Chain abilities (if any)
```

**13 trigger types**: Ongoing, OnPlay, OnPlayOther, StartOfTurn, EndOfTurn, OnDraw,
OnDrawOther, OnDeath, OnDeathOther, OnDamaged, BattleStart, BattleEnd, + secrets/traps

**12 target types**: None, CardSelf, CharacterSelf, AllCharacters, AllCardsHand,
AllCardsAllPiles, AllSlots, AllCardData, PlayTarget, AbilityTriggerer, + more

### 3. Effects Engine (40+ types)

| Category | Effects |
|----------|---------|
| **Combat** | Damage, DamageHalf, DamageRandom, Heal |
| **Stats** | AddStat, MultStat, SetStat, ResetStat, AddStatDelayed, AddStatRoll, AddStatCount |
| **Resources** | Draw, Discard, GainMana, GainCard, GainItem, RemoveCard, RemoveItem |
| **Status** | AddTrait, RemoveTrait, SetTrait, AddAbility, RemoveAbility, ClearStatus, RemoveStatus |
| **Card Manipulation** | Create, SummonCard, SummonCharacter, TransformCard, TransformCharacter, UpgradeCard |
| **Complex** | Repeat, Roll, SelectedValue, SetTarget, Play, Consume, Destroy, Resurrect, Steal |
| **Meta** | RedrawHand, SendPile, ClearTemp, MapOngoingBoost |

**Base class**: `EffectData : ScriptableObject` with virtual `DoEffect()` overloads
for BattleCharacter, Card, Slot, and CardData targets.

### 4. Conditions & Filters (30+ conditions, 4 filters)

| Category | Conditions |
|----------|-----------|
| **Character State** | Alive, Damaged, Status, Stat, StatSelf |
| **Card State** | CardData, CardPile, PlayTarget, Once |
| **Positioning** | CharacterBack, CharacterFront, SlotEmpty, SlotValue |
| **Ownership** | Ally, Owner, Self, Side, Target |
| **Game State** | Turn, TurnCount, Level, Map, Scenario, Rolled, SelectedValue |
| **Traits** | Trait, Type, SameData, Count, CountTarget, Item |

**Filters**: FilterRandom (N random), FilterFirst (first N), FilterHighestStat, FilterLowestStat

### 5. Battle System

**State machine** (BattlePhase):
```
None → StartTurn → Main → EndTurn → (next character) → ... → Ended
```

**Board**: Slot grid — x: 1-4, enemy: bool (player side / enemy side)

**BattleCharacter** (runtime): hp, shield, mana, damage, speed, hand size, energy,
card piles (deck, hand, discard, power, item, void, temp), traits, status effects,
abilities, action history.

**Initiative**: Turn order list, characters act in sequence.

**ResolveQueue**: Async effect resolution with timing for animations.

### 6. Status Effects (23 types)

| Category | Effects |
|----------|---------|
| **Offensive** | AttackPower, MagicPower, Poisoned, Burned, Thorn |
| **Defensive** | Armor, Evasive, StatusResistance, BurnHeal |
| **Control** | Stunned, Sleep, Fearful, Vulnerable |
| **Buffs** | Courageous, SpeedBonus, HandBonus, ManaCostBonus |
| **Card** | Keep (card not discarded at end of turn) |

**Duration types**: Persistent (until removed), AutoReduce (-1/turn), OneTurn (cleared at end of turn)

### 7. Champion & Character System

**ChampionData** (ScriptableObject): stats, level scaling, starting deck, starting items,
team affiliation, reward card pools.

**Champion** (runtime): persistent across run — hp, damage, speed, hand, energy,
deck (ChampionCard list), inventory, allies, gold/xp multipliers.

**Level scaling**: hp, speed, hand, energy all have per-level-up increments.

**Asset count**: 43 characters total

### 8. AI System

```
AIPlayer (abstract)
└── AIPlayerBehavior (concrete — reads battle state, calls BattleLogic actions)

BehaviorData (abstract ScriptableObject)
├── BehaviorBoss      — Strategic, multi-phase
├── BehaviorRandom    — Naive random selection
└── BehaviorSequence  — Fixed action sequence
```

AI runs in Update(), reads `GetBattleData()`, calls `PlayCard()`, `SelectCharacter()`, etc.

### 9. Map & Progression

**MapData**: depth, width range, fork probability, event assignment per depth.

**Map generation**: procedural branching paths with straight + diagonal links.

**MapLocation**: depth, index, event, adjacency list, visited/completed state.

**WorldState machine**:
```
None → Setup → Map → Battle/Event/Choice/Reward/Shop/Upgrade → ... → (loop through maps)
```

**ScenarioData**: difficulty config — champion count, starting gold/xp, enemy stat
multipliers, map sequence.

**Event types** (10): Battle, BattleFixed, Choice, Shop, Reward, Upgrade, Gain, Lose,
Trade, Text, Random.

**Asset count**: 6 maps, 134 events, 10 scenarios

### 10. Save System

- `World` class is `[Serializable]` (Battle excluded — circular refs)
- Binary serialization via `SaveTool`
- Saves persistent run state (champions, inventory, map progress)

### 11. UI Architecture

**Base class**: `UIPanel` — CanvasGroup fade in/out, Show/Hide/Toggle lifecycle.

**Key panels**: BattleUI (HUD), ShopPanel, RewardPanel, UpgradePanel, CollectionPanel,
DeckPanel, EndGamePanel, GameOverPanel, SettingsPanel, MapPanel, ChampionPanel.

**Card display**: CardUI (universal), CardUIHover (tooltips), HandCard (playable),
CardGrid (layout), CardPreviewUI (zoom).

**Combat UI**: StatusIcon, IntentIcon, InitiativeBar, PowerBar, SelectTargetUI.

**Asset count**: 70 UI scripts, 38 UI prefabs

### 12. Scenes (8)

| Scene | Purpose |
|-------|---------|
| Menu | Main menu |
| LoginMenu | Account/login |
| GameSetup | Pre-battle draft |
| Map | Run navigation |
| BattleForest | Combat (forest) |
| BattleVolcano | Combat (volcano) |
| Server | Network management |
| CardExporter | Editor tool |

### 13. VFX

60+ particle prefabs covering attacks, magic, status effects, spawns, card animations,
and environmental effects.

---

## Key Technical Patterns

| Pattern | Usage |
|---------|-------|
| **ScriptableObject data-driven** | All game content defined as assets, not code |
| **Polymorphic effects** | Base EffectData with virtual DoEffect — new effects = new subclass |
| **Polymorphic conditions** | Same pattern for ConditionData and FilterData |
| **Singleton facade** | GameManager coordinates all subsystems |
| **Static event bus** | GameEvents for decoupled UI/FX subscriptions |
| **Object pooling** | Pool class for reusable objects, ListSwap for GC-free lists |
| **Trigger caching** | Cards pre-indexed by trigger type for O(1) lookup |
| **ResolveQueue** | Async resolution with timing for animation sync |

---

## Asset Scale Summary

| Category | Count |
|----------|-------|
| Cards | 225 |
| Abilities | 272 |
| Events | 134 |
| Effects | 114 |
| Conditions | 110 |
| Status Effects | 46 |
| Characters | 43 |
| Traits | 20 |
| Teams | 16 |
| Intents | 12 |
| Scenarios | 10 |
| Rarities | 8 |
| Behaviors | 8 |
| Maps | 6 |
| **Total data assets** | **~1,072** |

---

## Open Questions for Design Phase

These need answers when creative direction is defined:

1. **Theme & identity** — What makes this game distinct from the base RogueEngine?
2. **Core pillars** — What 3 feelings should the player experience?
3. **Champion differentiation** — How do champions play differently from each other?
4. **Progression depth** — Meta-progression between runs? Unlocks?
5. **Difficulty curve** — How does ScenarioData difficulty scaling feel?
6. **Card design philosophy** — Simple cards with complex combos, or complex cards?
7. **AI sophistication** — Are 3 behavior types enough, or do enemies need more variety?
8. **Map variety** — 6 maps sufficient, or need procedural variety?
9. **Multiplayer** — Server scene exists. Is multiplayer planned?
10. **Monetization** — Free? Premium? Any live-service elements?

These will be addressed via `/brainstorm` and `/design-system`.

