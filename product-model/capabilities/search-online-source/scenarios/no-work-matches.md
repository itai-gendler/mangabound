---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User searches for a title with extra characters in it
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Online source
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The Product says nothing matches and suggests a simpler title
    kind: condition
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
---

# No work matches

## Trigger

The title typed is not how the source knows the work.

## Outcome

No match is listed; the User can search again or group the chapters by hand.
