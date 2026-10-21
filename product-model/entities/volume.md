---
domain: chapter-mapping
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#addVolume
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#splitVolume
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#mergeVolumes
---

# Volume

One volume of a chapter mapping: a number and the chapters in it. Each volume becomes one book, unless the series is made into one book, where it is a level of that book.

## Information kept

- **Number** — whole or decimal, such as 3 or 1.5, at most 100000, and used by one volume only once the mapping is confirmed
- **Chapters** — the chapters it holds, in chapter order
