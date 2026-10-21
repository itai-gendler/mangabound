---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User opens the book details of a folder whose chapter names say pt-br, for EPUB books
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
          - Language
      - entity: conversion-options
        effect: reads
        facts:
          - Format
    contexts:
      desktop:
        place: desktop::book-details
  - text: The User chooses Use pt-BR
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Language
    contexts:
      desktop:
        place: desktop::book-details
---

# Use the language the folder names declare

## Trigger

The manga is in another language than the one the conversion options give EPUB books.

## Outcome

The books will carry pt-BR. Nothing changed until the button was used; for a CBZ or PDF there is no button, only a note that just EPUB files carry a language.
