---
domain: ready-books
references:
  - kind: code
    role: implementation
    target: src/application/workflows/book-production.ts#BookProduction
  - kind: code
    role: implementation
    target: src/library/manifest.ts#parseLibraryManifest
  - kind: code
    role: implementation
    target: src/domain/book-warnings.ts#warningNotices
  - kind: adr
    role: intent
    target: docs/adr/0029-books-of-one-run-never-replace-each-other.md
  - kind: adr
    role: intent
    target: docs/adr/0039-mangapress-warnings-are-shown-with-the-results.md
---

# Ready book

One book a run made, waiting in its pending conversion. It can be saved, opened and shared until its conversion is deleted or cleaned up.

## Information kept

- **Name** — its file name, unique within its conversion
- **Format** — EPUB, CBZ or PDF
- **Size** — how big the file is
- **Title** — the title it carries
- **Author** — the author it carries; a CBZ carries none
- **Made at** — when it was converted
- **Warnings** — what mangapress or mangabind noticed and went on from, such as pages smaller than the screen or chapters left out
- **Saved to** — where its last saved copy is

## States

### Not saved yet

Only the pending copy exists.

### Saved

A copy was saved and recorded in the folder it went to; the pending copy stays until its conversion is removed.
