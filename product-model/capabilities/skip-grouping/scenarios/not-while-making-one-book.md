---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User looks for Skip grouping with Create one book for the series on
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - One book for the series
    contexts:
      desktop:
        place: desktop::volume-editor
  - text: Skip grouping is unavailable, because one book for the series needs the chapters grouped
    kind: condition
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - One book for the series
    contexts:
      desktop:
        place: desktop::volume-editor
---

# Not while one book is made of the series

## Trigger

The queue makes one book of each series.

## Outcome

The steps stay as they are; the volumes are needed to put each chapter under its volume.
