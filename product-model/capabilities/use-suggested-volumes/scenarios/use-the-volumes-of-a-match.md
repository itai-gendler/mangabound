---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Use these volumes on the matching work
    kind: actor
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: MangaDex is asked for the work's volumes in the language the chapter names declare, and in English when that language has none
    kind: product
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product puts each chapter the work lists in the Volume of that number, creating the volumes missing, and records MangaDex as the source of the Chapter mapping
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: creates
        facts:
          - Number
          - Chapters
      - entity: chapter-mapping
        effect: changes
        facts:
          - Origin
          - Source
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The summary of the suggested volumes is shown, Suggested by MangaDex, to confirm or edit
    kind: condition
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Origin
          - Source
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Use the volumes of a match

## Trigger

The User found the work in the online source.

## Outcome

The chapters are grouped as the source groups them; a chapter the source does not list keeps its place, unassigned if it had none, and the suggestion is checked before it is confirmed.
