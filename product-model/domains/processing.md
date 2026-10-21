---
references:
  - kind: adr
    role: intent
    target: docs/adr/0056-the-app-works-in-a-folder-a-person-can-choose.md
---

# Processing

The Processing tab of App settings: the folder the app works in, the books waiting to be saved and their clean-up, and what the app does while it converts.

## Boundary

It owns where and how the app works. It does not own running a conversion, which is the Queue, nor what a book is made with.
