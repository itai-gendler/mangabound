---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User opens the details of one Library title
    kind: actor
    actor: user
    entities:
      - entity: library-title
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::library-titles
  - text: The User types its author
    kind: actor
    actor: user
    entities:
      - entity: library-title
        effect: changes
        facts:
          - Author
    contexts:
      desktop:
        place: desktop::book-details
  - text: Leaving the page keeps the author in the title folder's mangabind.json
    kind: product
    actor: user
    entities:
      - entity: library-title
        effect: reads
        facts:
          - Author
          - Language
    contexts:
      desktop:
        place: desktop::library-titles
---

# Set the details of a library title

## Trigger

A library holds series by different authors.

## Outcome

That title's books carry its own author, and the library brings it back the next time it is read.
