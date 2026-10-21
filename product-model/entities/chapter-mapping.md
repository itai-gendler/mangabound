---
domain: chapter-mapping
relations:
  - entity: volume
    verb: holds
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#validateMapping
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#toMangabindMetadata
  - kind: code
    role: implementation
    target: src/adapters/mangabind/binding-port.ts#MangabindBindingAdapter
  - kind: adr
    role: intent
    target: docs/adr/0008-mapping-starts-from-mangabind-grouping.md
---

# Chapter mapping

Which chapters of one manga belong to which volume: what mangabind joins the books from. It starts from mangabind's own grouping of the chapter names. Edits in the volume editor become the item's mapping when it is confirmed, and a changed mapping is kept in the manga folder's mangabind.json.

## Information kept

- **Chapters** — the chapters read from the folder names, each with its number, pages, and any volume or language its name declares
- **Origin** — grouped from the file names, built by hand, or suggested by an online source
- **Source** — the online source and work a suggestion came from, recorded as "Suggested by MangaDex"
- **Unassigned chapters** — the chapters no volume holds, which are left out of the books

## States

### Proposed

As read or as edited, not confirmed yet: a folder whose every chapter has a volume can still be processed.

### Confirmed

Accepted in the volume editor, gaps included: it is the grouping the next run uses.
