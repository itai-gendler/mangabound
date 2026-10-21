---
appliesTo:
  - type: capability
    id: close-mangabound
  - type: entity
    id: pending-conversion
    effect: removes
references:
  - kind: code
    role: implementation
    target: src/main/quit-cleanup.ts#cleanUpBeforeQuit
  - kind: code
    role: implementation
    target: src/adapters/library/fs-pending-runs.ts#FsPendingRuns
---

# A conversion whose books are all saved is removed when Mangabound closes

When the app closes, after sharing has stopped, each pending conversion whose every book was saved is removed; one with a book not saved yet stays for the next launch, however old.
