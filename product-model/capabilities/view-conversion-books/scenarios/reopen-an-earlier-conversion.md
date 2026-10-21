---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User opens View books on a Pending conversion under Ready books
    kind: actor
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Made at
          - Books
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
  - text: The results list every Ready book of it, saved or not, without the warnings it was made with
    kind: condition
    actor: user
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
          - Format
          - Size
          - Saved to
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
    contexts:
      desktop:
        place: desktop::results
---

# Reopen an earlier conversion

## Trigger

The app was closed before the books of a run were saved.

## Outcome

The books of that conversion are listed as Saved or Not saved yet, with the same actions as right after a run.
