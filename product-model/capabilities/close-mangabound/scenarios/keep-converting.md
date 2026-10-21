---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User closes Mangabound while a conversion runs
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::processing
  - text: Mangabound asks whether to close, since the conversion would be lost
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::processing
  - text: The User chooses Keep converting
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::processing
---

# Keep converting

## Trigger

The window was closed by habit during a long run.

## Outcome

The app stays open and the conversion goes on; the question comes once per attempt to leave.
