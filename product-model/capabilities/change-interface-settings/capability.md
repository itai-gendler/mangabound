---
availability:
  - place: desktop
references:
  - kind: code
    role: implementation
    target: src/renderer/components/settings/interface-tab.tsx
  - kind: code
    role: implementation
    target: src/domain/app-settings.ts#resolveLanguage
  - kind: adr
    role: intent
    target: docs/adr/0052-the-app-language-is-chosen-behind-a-gear.md
  - kind: adr
    role: intent
    target: docs/adr/0070-the-theme-may-follow-the-system.md
---

# Change Interface settings

Sets the Language and the Theme of the app in the Interface tab of App settings; each applies at once and is kept.
