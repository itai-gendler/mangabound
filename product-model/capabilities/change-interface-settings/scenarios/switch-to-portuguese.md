---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses Português (Brasil) as the language in App settings
    kind: actor
    actor: user
    entities:
      - entity: app-settings
        effect: changes
        facts:
          - Language
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The window speaks Brazilian Portuguese at once; books, titles and the tools' own messages stay as they are
    kind: condition
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Language
    contexts:
      desktop:
        place: desktop::app-settings
---

# Switch the app to Brazilian Portuguese

## Trigger

The User prefers Portuguese.

## Outcome

The app opens in Portuguese from now on.

## Edge cases

- Automatic (system language) uses the first language of the system the app has, a variety of it such as pt-PT for pt-BR, or English.
