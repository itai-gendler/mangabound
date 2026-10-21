---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User tries to confirm while a Volume holds chapter 2, which is in the folder twice
    kind: actor
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
          - Chapters
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The ready check lists Chapter 2 is in the folder more than once among the errors, and Confirm mapping is unavailable
    kind: condition
    actor: user
    entities:
      - entity: chapter-mapping
        effect: reads
        facts:
          - Chapters
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Errors keep the mapping from being confirmed

## Trigger

The mapping holds an error: a chapter whose copies mangabind cannot choose between, an empty volume, a number used twice, or a chapter placed in another volume than the one its name says.

## Outcome

Nothing is confirmed until the error is gone; for copies of a chapter, that means removing all but one from the folder and adding it again.
