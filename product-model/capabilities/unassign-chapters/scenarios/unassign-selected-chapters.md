---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User selects an extra chapter and unassigns it
    kind: actor
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product takes it out of its Volume and lists it with the unassigned chapters of the Chapter mapping
    kind: product
    actor: user
    entities:
      - entity: volume
        effect: changes
        facts:
          - Chapters
      - entity: chapter-mapping
        effect: changes
        facts:
          - Unassigned chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Unassign selected chapters

## Trigger

A chapter is not meant to be in any book.

## Outcome

The chapter is unassigned, and the ready check warns that it is not in a volume.
