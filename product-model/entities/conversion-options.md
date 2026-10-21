---
domain: conversion-options
singleton: true
references:
  - kind: code
    role: implementation
    target: src/domain/preferences.ts#defaultPreferences
  - kind: code
    role: implementation
    target: src/domain/output-profile.ts#defaultMangapressSettings
  - kind: code
    role: implementation
    target: src/application/workflows/preferences.ts#PreferencesWorkflow
  - kind: adr
    role: intent
    target: docs/adr/0014-persisted-settings-and-reset.md
  - kind: adr
    role: intent
    target: docs/adr/0045-cbz-is-the-format-a-first-launch-starts-with.md
---

# Conversion options

The queue's options: what every item is made with unless it sets options of its own. They are kept between launches, and a damaged value is put back to its default with a notice.

## Information kept

- **Steps** — Group chapters into volumes, Convert for e-reader, or both; both to start
- **One book for the series** — Create one book for the series; off to start
- **Device** — the e-reader profile; a Kindle Paperwhite to start, or Other with a custom size
- **Format** — CBZ to start, EPUB or PDF
- **Custom size** — Custom width and Custom height, in pixels
- **Advanced options** — the mangapress options grouped as Reading, Double-page spreads, Size and borders, Cropping, Two-page view, Color and tone, Page images, Cover and Book metadata, with Use the images as they are and Name the book .epub beside the device
- **Online source** — the online source last chosen for volume and author lookups
