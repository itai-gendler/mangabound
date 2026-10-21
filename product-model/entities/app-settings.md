---
singleton: true
references:
  - kind: code
    role: implementation
    target: src/domain/app-settings.ts#defaultKeptAppSettings
  - kind: code
    role: implementation
    target: src/application/workflows/app-settings.ts
  - kind: adr
    role: intent
    target: docs/adr/0052-the-app-language-is-chosen-behind-a-gear.md
  - kind: adr
    role: intent
    target: docs/adr/0068-how-many-are-converted-at-once-is-a-choice-a-queue-keeps.md
---

# App settings

What the person decided about the app itself, apart from the conversion options: kept as each change is made, left alone by Reset to defaults, and replaced by the defaults, with a notice, when the saved file cannot be read.

## Information kept

- **Language** — Automatic (system language), English or Português (Brasil)
- **Theme** — Automatic (system theme), Dark (graphite) or Light (paper)
- **Working folder** — Chosen by Mangabound, or a folder the person chose, inside which Pending and Scratch are made
- **Earlier working folders** — folders chosen before where books are still waiting; dropped once empty
- **Tell me when a long conversion ends** — on to start
- **Keep the computer awake while converting** — on to start
- **Parallel conversions** — Automatic, or a number from 1 to what this computer can be asked for, at most 12
