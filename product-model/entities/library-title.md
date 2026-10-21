---
domain: queue
relations:
  - entity: chapter-mapping
    verb: has
    cardinality: one-to-one
  - entity: book-cover
    verb: has
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#isPendingTitle
  - kind: code
    role: implementation
    target: src/domain/run-report.ts#reportLibraryRun
  - kind: code
    role: implementation
    target: src/application/workflows/library-run.ts#LibraryRun
  - kind: adr
    role: intent
    target: docs/adr/0012-libraries-in-the-queue.md
---

# Library title

One manga folder inside a library in the queue. It is grouped, given details and options, and made into books on its own, and the library keeps track of which of its titles are done.

## Information kept

- **Name** — the manga folder's name
- **Folders left out** — its folders whose names hold no chapter number
- **Title** — the series title typed for it; what was typed outlives the library being read again
- **Author** — who wrote it, kept in the title folder's mangabind.json
- **Language** — the language tag of its EPUB books, kept in the title folder's mangabind.json
- **Own options** — the conversion options it sets differently from the queue
- **Failure reason** — why the last run could not make its books

## States

### Needs volumes

No volume was found in its chapter names yet; a run leaves it out until it is grouped.

### Grouped

It has volumes, and the next run makes its books.

### Saved

A run made its books, which wait under Ready books; later runs leave it out.

### Failed

The last run could not make its books; the next run tries it again.
