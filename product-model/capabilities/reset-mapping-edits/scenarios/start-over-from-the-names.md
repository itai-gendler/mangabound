---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User starts over from the names on the File names tab
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Origin
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Chapter mapping goes back to the volumes found in the chapter names, and the edits are discarded
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: changes
        facts:
          - Number
          - Chapters
      - entity: chapter-mapping
        effect: changes
        facts:
          - Origin
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Start over from the names

## Trigger

The names already said the volumes, and the edits made them worse.

## Outcome

The volumes read from the names are back.
