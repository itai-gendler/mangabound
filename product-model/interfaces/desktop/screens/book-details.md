---
entities:
  - entity: queue-item
    shows:
      - Name
      - Title
      - Author
      - Language
    collects:
      - Title
      - Author
      - Language
  - entity: library-title
    shows:
      - Name
      - Title
      - Author
      - Language
    collects:
      - Title
      - Author
      - Language
  - entity: book-cover
    shows:
      - Book
      - Image name
      - Origin
  - entity: volume
    shows:
      - Number
  - entity: conversion-options
    shows:
      - Format
      - Online source
    collects:
      - Online source
references:
  - kind: code
    role: implementation
    target: src/renderer/screens/book-details-screen.tsx#BookDetailsScreen
  - kind: adr
    role: intent
    target: docs/adr/0030-title-author-and-language-belong-to-each-book.md
---

# Book details

The title, author and language of one item or library title, the book titles they give, and its Covers: one line for each book it makes.
