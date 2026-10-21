---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User chooses Webtoon strips under Reading
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
  - text: Manga reading order, the double-page spread options and the other options a webtoon never uses are dimmed, each saying why, with their values kept
    kind: condition
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Advanced options
    contexts:
      desktop:
        place: desktop::advanced-conversion-options
---

# Webtoon strips dim what they never use

## Trigger

The series is long vertical strips.

## Outcome

The strips are cut into pages; going back to manga or comic pages brings back what had been chosen.
