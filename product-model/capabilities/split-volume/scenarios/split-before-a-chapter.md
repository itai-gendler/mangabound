---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User splits volume 2 before chapter 15, giving the new volume number 3
    kind: actor
    actor: user
    entities:
      - entity: volume
        as: first
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: Chapter 15 and every later chapter move from the first Volume into a new Volume numbered 3
    kind: product
    actor: user
    entities:
      - entity: volume
        as: first
        effect: changes
        facts:
          - Chapters
      - entity: volume
        as: second
        effect: creates
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Split before a chapter

## Trigger

A volume holds the chapters of two volumes of the User's edition.

## Outcome

Two volumes take the chapters of the one, split where the User chose.
