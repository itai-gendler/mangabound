---
kind: edge
routes:
  desktop: Desktop
steps:
  - text: The User searches while the computer is offline
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
  - text: The Product says the search failed; grouping by hand on Manual is still there
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

# The source cannot be reached

## Trigger

The online source does not answer.

## Outcome

Nothing changes in the mapping; an error from an online source never stops grouping by hand.
