---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User confirms the volumes of a Library title that needed volumes
    kind: actor
    actor: user
    entities:
      - entity: library-title
        effect: reads
        facts:
          - Name
      - entity: chapter-mapping
        effect: reads
        facts:
          - Unassigned chapters
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product writes the Chapter mapping into the title folder's mangabind.json, keeping the author, the language and every other key the file holds
    kind: product
    actor: user
    entities:
      - entity: chapter-mapping
        effect: changes
        from: Proposed
        to: Confirmed
        facts: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: mangabind reads the library again, and the Library title is grouped while titles already saved stay saved
    kind: product
    actor: user
    entities:
      - entity: library-title
        effect: changes
        from: Needs volumes
        to: Grouped
        facts: []
    contexts:
      desktop:
        place: desktop::library-titles
---

# Confirm the volumes of a library title

## Trigger

A title of a library had no volumes in its chapter names, and the User grouped it.

## Outcome

The title now shows its volumes in the list of titles, and the grouping is kept in its folder for every later run.
