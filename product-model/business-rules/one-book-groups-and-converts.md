---
appliesTo:
  - type: capability
    id: change-conversion-options
  - type: capability
    id: skip-grouping
  - type: capability-scenario
    id: make-one-book-for-the-series
references:
  - kind: code
    role: implementation
    target: src/application/workflows/run-preconditions.ts#assertSingleBook
  - kind: adr
    role: intent
    target: docs/adr/0025-single-book-mode-workflow-control.md
  - kind: adr
    role: intent
    target: docs/adr/0081-a-series-made-into-one-book-can-be-an-epub-a-cbz-or-a-pdf.md
---

# One book for the series both groups and converts

With Create one book for the series on, both steps are on and locked, and grouping cannot be skipped: the volumes are what each chapter is placed under. The format stays the person's choice and decides what the book holds: an EPUB has the volumes and chapters in its table of contents, a CBZ keeps them as folders, a PDF has the pages in order. A queue of CBZ files alone keeps the choice for later folders but makes nothing of it.
