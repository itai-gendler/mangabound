---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User opens the options of one Library title
    kind: actor
    actor: user
    entities:
      - entity: library-title
        effect: reads
        facts:
          - Name
          - Own options
    contexts:
      desktop:
        place: desktop::library-titles
  - text: The User turns on Webtoon strips for it
    kind: actor
    actor: user
    entities:
      - entity: library-title
        effect: changes
        facts:
          - Own options
    contexts:
      desktop:
        place: desktop::item-options
---

# Options of a library title

## Trigger

One series of a library is a webtoon.

## Outcome

That title is made with webtoon strips, the others with the queue's options; what was chosen for it survives the library being read again.
