---
references:
  - kind: adr
    role: intent
    target: docs/adr/0014-persisted-settings-and-reset.md
---

# Conversion settings

How the queue's items are made into books: the steps, device, format and every mangapress option, for the whole queue and for one item that differs.

## Boundary

It owns the options a book is made with. It does not own the choices about the app itself in App settings, such as where it works or how many books it converts at once.
