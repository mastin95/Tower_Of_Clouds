# Conflict Resolution Playbook

The Director encounters conflicts when subagent outputs pull in incompatible directions. This file documents how to handle each type.

---

## Conflict Type 1: Lore ↔ Mechanic

**What it looks like:** A `world-architect` output establishes something about how the world works that makes a `game-designer` output incoherent, or vice versa.

**Example:** World Architect designs gods that are emotionally distant and unknowable. Game Designer designs a mechanic where you negotiate directly with gods mid-run. These create friction.

**Resolution ladder:**
1. **Check the Pillars first.** Which version better serves the core theme and tone? That version wins.
2. **Look for the synthesis.** Can both be true at once? (e.g., gods are distant *unless* you've accumulated enough Faith — then they notice you)
3. **Flag as a design decision.** If neither synthesis feels right, present both to the user as a fork. Explain what each implies for the game feel.

**Never:** Discard one output silently. Always document the tension.

---

## Conflict Type 2: Tone Mismatch

**What it looks like:** Two outputs feel like they belong to different games. One is grimly serious; one is playfully subversive. One is mythic and grand; one is intimate and human.

**Resolution ladder:**
1. **Identify which output is drifting.** Usually one of them is clearly more aligned with established tone.
2. **Reframe the drifting output.** Can it be rephrased without losing its core content so it fits the established tone?
3. **If both feel right but different:** This may be a genuine tonal question — present it as such. "The game can lean into [tone A] or [tone B] here. These aren't the same game." Let the user choose.

---

## Conflict Type 3: Scope Creep

**What it looks like:** A subagent output correctly executes its brief but implicitly expands the game's scope in a direction the directive didn't sanction.

**Example:** Game Idea Forge is asked for "card ideas for the apostate archetype" and returns a fully developed faction system that would require a new game mode.

**Resolution:**
1. **Do not integrate the expansion.** Integrate only what fits the original scope.
2. **Flag the expansion prominently** in the "Unexpected gifts" section of the report.
3. **Propose it as a future session**, not a current one.

Scope creep is often genuinely good ideas at the wrong time. Protect them; don't act on them.

---

## Conflict Type 4: Contradiction with Established Canon

**What it looks like:** A subagent output contradicts something already established in the GDD, vault, or decision log.

**Resolution ladder:**
1. **Check if the canon item is locked.** Is it in the "locked constraints" section of the GDD? If yes: the new output must change, not the canon.
2. **Check if the canon item is draft.** If it's still marked as provisional: the new output might supersede it. Flag the potential revision and ask the user.
3. **Check if the contradiction is productive.** Sometimes a contradiction reveals that the canon item was wrong or under-examined. If so, flag it as a "design information" item — a signal that something needs revisiting.

---

## Conflict Type 5: Quality Mismatch

**What it looks like:** Two subagent outputs are at very different quality levels. One is deep and specific; one is generic and surface-level.

**Resolution:**
1. **Do not average them.** The weaker output drags the synthesis down.
2. **Use the stronger output as the baseline.** Re-brief the weaker skill with more specific constraints and the context from the stronger output.
3. **If time doesn't allow a re-brief:** Flag the gap in the report. "The lore for X is fully developed; the mechanic sketch for X is still a placeholder. Recommend a follow-up session."

---

## The Arbitration Log

After every Director session, maintain a brief log entry:

```
**Session:** [Directive summary]
**Conflicts encountered:** [List]
**How resolved:** [Method used]
**Design decisions implied:** [What does this resolution commit the game to?]
```

This log is the game's institutional memory for *why* things are the way they are. It prevents the team (you, future-you, collaborators) from relitigating settled questions.

---

## When to Escalate to the User

Escalate a conflict to the user when:
- Both options are equally valid and the choice has **long-term game design consequences**
- The conflict reveals a **fundamental ambiguity in the game's identity** that hasn't been resolved
- Resolution requires knowledge the Director doesn't have (e.g., "which feels better to play" — that requires a human judgment)

Do not escalate when:
- One option is clearly more thematically coherent
- The conflict is purely cosmetic (naming, phrasing)
- The conflict is between a locked canon item and new content (locked always wins)
