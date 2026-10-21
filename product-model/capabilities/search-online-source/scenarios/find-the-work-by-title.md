---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User picks MangaDex on the Online source tab
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Online source
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The User searches for the manga title
    kind: actor
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: MangaDex is sent the title and answers with the matching works, their authors and the year each began
    kind: product
    actor: user
    entities: []
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: The matches are listed, each with Use these volumes
    kind: condition
    actor: user
    entities:
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Find the work by its title

## Trigger

The chapter names hold no volume numbers and the User would rather not group them by hand.

## Outcome

The works that match are listed with who wrote them and when they began, so works with the same title can be told apart. The source chosen is remembered for the next time.
