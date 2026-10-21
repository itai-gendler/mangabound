---
appliesTo:
  - type: capability
    id: add-volume
  - type: capability
    id: change-volume-number
  - type: capability
    id: split-volume
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#isVolumeNumber
  - kind: adr
    role: intent
    target: docs/adr/0042-mangabind-0-7-pages-it-leaves-out-are-shown.md
---

# A volume number is whole or decimal, up to 100000

A volume number is digits, with an optional point and digits after it, such as 3 or 1.5, and no more than 100000, the highest mangabind takes; anything else is refused when it is typed.
