---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User opens Edit titles on a library's row
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: Each Library title shows its chapters and volumes, or that it needs volumes, was saved or failed, with the folders left out of it
    kind: condition
    actor: user
    entities:
      - entity: library-title
        effect: reads
        facts:
          - Name
          - Folders left out
          - Failure reason
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
          - Unassigned chapters
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::library-titles
  - text: The links to a series elsewhere are listed by name above the titles
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Links not followed
    contexts:
      desktop:
        place: desktop::library-titles
---

# Review the titles of a library

## Trigger

The User wants to check a library title by title before running it.

## Outcome

Every title is listed with its state, and each can be grouped, given details or given options of its own from here.
