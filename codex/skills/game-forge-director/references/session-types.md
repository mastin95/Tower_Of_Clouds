# Session Types — Common Directives & Skill Combinations

A lookup table for the Director. When a directive matches a pattern here, use the suggested combination as a starting point — but always adapt to the specific task and context.

---

## Pattern 1: "Expand the world / flesh out X"

**Examples:** "Expand the pantheon", "flesh out the history of the Tensar", "develop the magic system further"

**Skill sequence:**
1. `world-architect` → Generate the content (parallel: can run multiple domain tasks)
2. `game-design-critic` → Evaluate thematic coherence and player-facing impact
3. `game-designer` → Identify mechanic echoes (how does this lore touch cards/systems?)

**Director's synthesis focus:** Do the lore additions create new mechanical possibilities? Do they reinforce or complicate the Faith/Blasphemy duality?

---

## Pattern 2: "Design a new mechanic / system"

**Examples:** "Design a card type for apostates", "create a corruption mechanic", "how should relics work?"

**Skill sequence:**
1. `game-idea-forge` → Generate 3–5 mechanic variants (web search for genre precedents)
2. `game-designer` → Formalize the strongest variant into a proper system
3. `game-design-critic` → Evaluate for fun, clarity, and thematic fit
4. `world-architect` → Check lore consistency; add any required worldbuilding support

**Director's synthesis focus:** Does the mechanic feel inevitable given the world? Would a player understand it without reading the lore?

---

## Pattern 3: "I have an idea — take it further"

**Examples:** "What if the gods bleed when you blaspheme?", "I'm thinking about time-manipulation cards"

**Skill sequence:**
1. `game-idea-forge` → Lateral expansion (what does this imply? what adjacent ideas does it open?)
2. `world-architect` → Lore implications (what does this mean for the world's cosmology?)
3. `game-designer` → Mechanic sketch (how would this actually work in the deck?)
4. `game-design-critic` → Hard critique (does this make the game better or just weirder?)

**Director's synthesis focus:** Is this a surface idea or a deep one? Surface ideas are fun to expand. Deep ideas need to be protected — they may be load-bearing.

---

## Pattern 4: "Critique and improve X"

**Examples:** "Is the Tensar mechanic working?", "critique the Faith meter design", "is this card fun?"

**Skill sequence:**
1. `game-design-critic` → Full critique (MDA, Schell lenses, SDT, Koster)
2. `game-designer` → Propose specific fixes based on critique
3. *(optional)* `game-idea-forge` → Generate alternative approaches if the fix requires rethinking the concept

**Director's synthesis focus:** What's the minimum change that fixes the identified problem? Avoid scope creep — a critique session should leave the game more coherent, not larger.

---

## Pattern 5: "Plan the next development phase"

**Examples:** "What should I work on next?", "help me prioritize", "what's the critical path?"

**Skill sequence:**
1. `project-manager` → Read current task board and decision log
2. `game-design-critic` → Identify the biggest current design risks
3. `game-designer` → Surface unresolved mechanical dependencies
4. Director synthesizes into a prioritized session plan

**Director's synthesis focus:** What is the single most load-bearing unresolved question in the game right now? That goes first.

---

## Pattern 6: "Full creative session on X"

**Examples:** "Let's do a full session on the Blasphemy system", "deep dive on the endgame"

This is a multi-pattern session. The Director should:
1. Decompose into 2–3 sub-sessions (expand → formalize → critique)
2. Present the decomposition to the user before starting
3. Run sub-sessions sequentially, reporting after each
4. Offer a cumulative synthesis at the end

**Cap at 2 hours / 3 sub-sessions per full session.** Longer than that, start a new Director session.

---

## Anti-Patterns — When NOT to use the Director

| Directive | Don't use Director | Use instead |
|---|---|---|
| "Write a god entry for X" | Too narrow | `world-architect` directly |
| "Is this card fun?" | Single question | `game-design-critic` directly |
| "Fix this bug in Unity" | No design work | `code-mentor` directly |
| "What should I add to the GDD?" | Project mgmt only | `project-manager` directly |
| "Give me 10 card ideas" | Ideation only | `game-idea-forge` directly |

The Director adds value through **coordination**. Single-skill tasks don't need coordination.
