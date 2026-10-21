---
kind: primary
result: achieved
routes:
  desktop: Desktop
steps:
  - text: The User presses Process
    kind: actor
    actor: user
    capability: process-queue
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
          - Device
          - Format
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product makes the Ready book of each Volume in a new Pending conversion and shows the results
    kind: product
    actor: user
    capability: process-queue
    entities:
      - entity: pending-conversion
        effect: creates
        facts:
          - Made at
          - Books
          - Size
          - Item results
      - entity: ready-book
        effect: creates
        to: Not saved yet
        facts:
          - Name
          - Format
          - Size
          - Title
          - Author
          - Made at
          - Warnings
        with: pending-conversion
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::results
  - text: The User chooses Save all to folder… and picks a folder
    kind: actor
    actor: user
    capability: save-all-books
    entities:
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::results
  - text: Each Ready book is copied under a free name, recorded in the Library folder and marked saved
    kind: product
    actor: user
    capability: save-all-books
    entities:
      - entity: ready-book
        effect: changes
        from: Not saved yet
        to: Saved
        facts:
          - Saved to
      - entity: library-folder
        effect: changes
        facts:
          - Recorded books
    contexts:
      desktop:
        place: desktop::results
---

# Process, then save all

## Trigger

The queue is ready and the User wants the books saved.

## Outcome

The books are in the chosen folder; their pending copies are removed when Mangabound closes.
