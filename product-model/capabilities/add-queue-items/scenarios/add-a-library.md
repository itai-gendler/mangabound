---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User adds a folder that holds several manga folders with Folder
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
  - text: mangabind reads the folder as one manga and finds no chapter with pages of its own
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Location
    contexts:
      desktop:
        place: desktop::queue
  - text: mangabind reads the folder again as a library, and the Queue item becomes a library
    kind: product
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        from: Checking
        to: Read
        facts:
          - Kind
          - Links not followed
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product adds a Library title for each manga folder with chapters, grouped where its names declare volumes, with the author and language its folder keeps
    kind: product
    actor: user
    entities:
      - entity: library-title
        as: grouped
        effect: creates
        to: Grouped
        facts:
          - Name
          - Folders left out
          - Author
          - Language
      - entity: library-title
        as: ungrouped
        effect: creates
        to: Needs volumes
        facts:
          - Name
          - Folders left out
          - Author
          - Language
      - entity: chapter-mapping
        as: grouped-mapping
        effect: creates
        to: Proposed
        facts:
          - Chapters
          - Origin
          - Unassigned chapters
        with: grouped
      - entity: chapter-mapping
        as: ungrouped-mapping
        effect: creates
        to: Proposed
        facts:
          - Chapters
          - Origin
          - Unassigned chapters
        with: ungrouped
      - entity: volume
        effect: creates
        facts:
          - Number
          - Chapters
        with: grouped-mapping
    contexts:
      desktop:
        place: desktop::queue
  - text: The row counts the titles a run would make books of, and notes the Library title that still needs grouping
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Kind
          - Name
      - entity: library-title
        as: grouped
        effect: reads
        facts:
          - Name
      - entity: library-title
        as: ungrouped
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::queue
---

# Add a library of manga folders

## Trigger

The User keeps several series in one folder and adds that folder rather than each series.

## Outcome

The folder is one library item in the queue, with a title for each manga in it. A title whose names declared no volume needs grouping before a run makes its books; the others are ready.

## Edge cases

- Folders of the library that are links to a series elsewhere are not read, and the row names them.
- A folder whose manga are all links holds no titles, and its row says why rather than suggesting to skip grouping.
- Only a library one level deep is read: a folder of libraries is not.
