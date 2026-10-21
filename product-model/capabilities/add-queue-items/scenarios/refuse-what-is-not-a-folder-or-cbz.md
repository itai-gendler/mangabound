---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User drops a PDF file on the queue
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product leaves it out and says that only folders and .cbz files can be added
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::queue
---

# Something that is neither a folder nor a CBZ

## Trigger

What the User adds is not a folder or a .cbz file.

## Outcome

Nothing is added for it; a dismissible message names it and says why.
