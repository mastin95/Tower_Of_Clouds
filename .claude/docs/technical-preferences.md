# Technical Preferences

<!-- Populated by /setup-engine. Updated as the user makes decisions throughout development. -->
<!-- All agents reference this file for project-specific standards and conventions. -->

## Engine & Language

- **Engine**: Unity 6.3 LTS (6000.3)
- **Language**: C#
- **Rendering**: URP (Universal Render Pipeline) — confirm with user
- **Physics**: Unity Physics (PhysX default)

## Naming Conventions

- **Classes**: PascalCase (e.g., `PlayerController`)
- **Public fields/properties**: PascalCase (e.g., `MoveSpeed`)
- **Private fields**: _camelCase (e.g., `_moveSpeed`)
- **Methods**: PascalCase (e.g., `TakeDamage()`)
- **Events/Delegates**: PascalCase with `On` prefix (e.g., `OnCardPlayed`)
- **Files**: PascalCase matching class (e.g., `PlayerController.cs`)
- **Scenes/Prefabs**: PascalCase (e.g., `MainMenu.unity`, `CardPrefab.prefab`)
- **Constants**: UPPER_SNAKE_CASE or PascalCase (e.g., `MAX_HAND_SIZE`)

## Performance Budgets

- **Target Framerate**: [TO BE CONFIGURED]
- **Frame Budget**: [TO BE CONFIGURED]
- **Draw Calls**: [TO BE CONFIGURED]
- **Memory Ceiling**: [TO BE CONFIGURED]

> Typical targets: 60fps / 16.6ms frame budget. Configure when ready.

## Testing

- **Framework**: Unity Test Framework (NUnit)
- **Minimum Coverage**: [TO BE CONFIGURED]
- **Required Tests**: Balance formulas, gameplay systems, card effects, deck mechanics

## Forbidden Patterns

<!-- Add patterns that should never appear in this project's codebase -->
- [None configured yet — add as architectural decisions are made]

## Allowed Libraries / Addons

<!-- Add approved third-party dependencies here -->
- Odin Inspector (Sirenix) — serialization and editor tooling
- RogueEngine — base deckbuilder asset (heavily modified)

## Architecture Decisions Log

<!-- Quick reference linking to full ADRs in docs/architecture/ -->
- [No ADRs yet — use /architecture-decision to create one]
