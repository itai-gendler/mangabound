---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User chooses a CBZ file with Files
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product adds a Queue item for the file and checks it
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: creates
        to: Checking
        facts:
          - Kind
          - Name
          - Location
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product takes the CBZ as already complete, with no chapters to group
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        from: Checking
        to: Read
        facts: []
    contexts:
      desktop:
        place: desktop::queue
---

# Add a complete volume as a CBZ

## Trigger

The User has a volume that is already one CBZ.

## Outcome

The CBZ is in the queue as Ready: it goes straight to the e-reader step. A single chapter CBZ added this way is a volume of its own; its folder is added instead to group it with the other chapters.
