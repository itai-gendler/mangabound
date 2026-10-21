---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User turns on Create one book for the series
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - One book for the series
    contexts:
      desktop:
        place: desktop::queue
  - text: Both steps of the Conversion options are turned on and locked, and the note says what the chosen format will hold
    kind: product
    actor: user
    entities:
      - entity: conversion-options
        effect: changes
        facts:
          - Steps
    contexts:
      desktop:
        place: desktop::queue
---

# Create one book for the series

## Trigger

The User wants each series in one book.

## Outcome

Each manga folder will be one book: an EPUB with volumes and chapters in its table of contents, a CBZ with them as folders, or a PDF with the pages in order. The steps stay locked until the mode is turned off.
