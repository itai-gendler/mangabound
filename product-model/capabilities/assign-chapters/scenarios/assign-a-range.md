---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User chooses chapter 10 From and chapter 18 Through for volume 2
    kind: actor
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
  - text: The Product puts every chapter from the first to the last, both included, in the Volume
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

# Assign a chapter range

## Trigger

A volume is a run of consecutive chapters.

## Outcome

Volume 2 holds chapters 10 through 18.
