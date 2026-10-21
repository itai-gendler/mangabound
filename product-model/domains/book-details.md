---
references:
  - kind: adr
    role: intent
    target: docs/adr/0040-a-cover-of-the-persons-own-for-each-book.md
---

# Book details and covers

What names the books of one item and what they look like on the shelf: the title, author and language, and a cover of the person's own for each book.

## Boundary

It owns the details and covers of an item. It does not own the volumes the books are made from, nor the conversion options, the cover options among them included.
