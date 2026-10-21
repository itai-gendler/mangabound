---
appliesTo:
  - type: capability
    id: assign-chapters
  - type: capability
    id: confirm-chapter-mapping
  - type: entity
    id: volume
    facts:
      - Chapters
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#validateMapping
---

# A chapter whose name says its volume stays in that volume

When a chapter's file name declares a volume, such as Vol.02 Ch.010, mangabind keeps the chapter in that volume whatever the mapping says. Placing it in another volume is allowed while editing, but the ready check lists it as an error until it is back in the volume its name declares or the folder is renamed.
