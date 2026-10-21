---
appliesTo:
  - type: capability
    id: search-online-source
  - type: capability
    id: use-suggested-volumes
  - type: capability
    id: find-author
references:
  - kind: adr
    role: intent
    target: docs/adr/0013-online-sources-for-volume-data.md
  - kind: doc
    role: intent
    target: docs/adding-a-metadata-provider.md
---

# Nothing is sent to an online source until the person searches

An online source is asked only when the person searches or uses a match, and is sent the title typed, the work chosen and the language of the folders, never pages, files or paths. Its answer is a suggestion to review, never required; volumes are looked up in the language the chapter names declare, then in English.
