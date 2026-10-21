---
entities:
  - entity: app-settings
    shows:
      - Language
      - Theme
      - Working folder
      - Earlier working folders
      - Tell me when a long conversion ends
      - Keep the computer awake while converting
      - Parallel conversions
    collects:
      - Language
      - Theme
      - Tell me when a long conversion ends
      - Keep the computer awake while converting
      - Parallel conversions
  - entity: pending-conversion
    shows:
      - Books
      - Size
references:
  - kind: code
    role: implementation
    target: src/renderer/components/settings/app-settings-menu.tsx
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/app-settings.mdx
  - kind: adr
    role: intent
    target: docs/adr/0055-the-settings-dialog-has-a-fixed-size.md
---

# App settings dialog

Choices about the app itself, kept as they are made, in four tabs: Interface, Processing, Updates and About. The conversion options stay in the queue.
