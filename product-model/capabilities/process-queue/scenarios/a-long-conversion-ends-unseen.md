---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User presses Process and goes to another window
    kind: actor
    actor: user
    entities:
      - entity: conversion-options
        effect: reads
        facts:
          - Steps
    contexts:
      desktop:
        place: desktop::queue
  - text: The Product starts a Pending conversion and keeps the computer awake while the queue runs
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: creates
        facts:
          - Made at
      - entity: app-settings
        effect: reads
        facts:
          - Keep the computer awake while converting
    contexts:
      desktop:
        place: desktop::processing
  - text: mangapress converts the volumes into ready books
    kind: product
    actor: user
    entities:
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
      - entity: pending-conversion
        effect: changes
        facts:
          - Books
          - Size
          - Item results
      - entity: volume
        effect: reads
        facts:
          - Number
    contexts:
      desktop:
        place: desktop::processing
  - text: The queue took more than 30 seconds, no Mangabound window is in front, and the App settings ask to be told
    kind: condition
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Tell me when a long conversion ends
    contexts:
      desktop:
        place: desktop::results
  - text: The system shows a notification of how many books of the Pending conversion are ready, or that some failed
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
          - Item results
    contexts:
      desktop:
        place: desktop::results
---

# A long conversion ends while nobody is looking

## Trigger

A long queue runs while the person works in another window.

## Outcome

A system notification says the books are ready, with notes or with failures; selecting it brings Mangabound back to the results. Nothing is shown for a queue the person stopped.
