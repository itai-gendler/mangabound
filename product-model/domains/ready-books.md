---
references:
  - kind: adr
    role: intent
    target: docs/adr/0026-process-then-save-pending-books.md
---

# Ready books

The books runs have made, waiting on this computer: listing them, saving, opening and finding them, offering them to the e-reader, and deleting a pending conversion.

## Boundary

It owns the pending conversions and their books. It does not own the sharing server itself (Sharing), nor the clean-up of what has waited long, which is in Processing.
