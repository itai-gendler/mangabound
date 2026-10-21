---
appliesTo:
  - type: capability
    id: confirm-chapter-mapping
  - type: entity
    id: chapter-mapping
    effect: changes
    to: Confirmed
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#validateMapping
  - kind: adr
    role: intent
    target: docs/adr/0039-mangapress-warnings-are-shown-with-the-results.md
---

# A chapter mapping with errors cannot be confirmed

The ready check lists as errors a volume with no chapters, a volume number used twice, a chapter that is in the folder more than once, a chapter placed in another volume than the one its name says, and a chapter mangabind.json cannot represent; Confirm mapping waits until none is left. Chapters with no volume are only a warning: confirming accepts them as left out of the books.
