---
references:
  - kind: adr
    role: intent
    target: docs/adr/0010-input-queue.md
---

# Queue and runs

What is waiting to become books: adding folders, libraries and CBZ files, taking them out again, checking the plan, and processing what is ready.

## Boundary

It owns the queue's items and the runs that process them. It does not own an item's volumes (Chapter mapping), its book details and covers (Book details), the options it is converted with (Conversion options), or the books once a run has made them (Ready books).
