---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User drops a folder of chapter folders on the queue
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product adds a Queue item for the folder and starts reading it
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
  - text: mangabind reads the chapter names, and the Product proposes a Chapter mapping with a Volume for each volume number the names declare
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        from: Checking
        to: Read
        facts:
          - Folders left out
          - Author
          - Language
      - entity: chapter-mapping
        effect: creates
        to: Proposed
        facts:
          - Chapters
          - Origin
          - Unassigned chapters
      - entity: volume
        effect: creates
        facts:
          - Number
          - Chapters
        with: chapter-mapping
    contexts:
      desktop:
        place: desktop::queue
  - text: The row shows the Queue item with its chapter count and how many volumes the names gave
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Kind
          - Name
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
        place: desktop::queue
---

# Add a manga folder

## Trigger

The User has a manga whose chapters are separate folders or separate chapter CBZs.

## Outcome

The folder is in the queue, read and grouped by the volume numbers in its chapter names, with the author and language its mangabind.json keeps already filled in. Folders whose names hold no chapter number are named as left out.

## Edge cases

- A folder or file already in the queue is not added a second time.
- Only the first 100 items of one add are taken, and a message says how many were left out.
- A folder in which no chapter is found says so, and suggests turning off Group chapters into volumes to convert it as one book.
