---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User resets the changed JPEG quality with the arrow beside it
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Advanced options
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
---

# Reset one changed field

## Trigger

Only one option should go back.

## Outcome

That option is at its default and the others stay as they were.
