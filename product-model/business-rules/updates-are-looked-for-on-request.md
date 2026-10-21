---
appliesTo:
  - type: capability
    id: check-for-updates
  - type: capability
    id: download-the-update
references:
  - kind: code
    role: implementation
    target: src/domain/update-check.ts#chooseUpdate
  - kind: adr
    role: intent
    target: docs/adr/0063-the-app-looks-for-a-newer-version-when-asked.md
---

# The app looks for a newer version only when asked

The check asks GitHub only on a click, counts pre-releases as every release so far is one, and leaves downloading and installing to the person.
