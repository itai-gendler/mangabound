---
kind: validation
routes:
  desktop: Desktop
steps:
  - text: The User types Portuguese as the language
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: changes
        facts:
          - Language
    contexts:
      desktop:
        place: desktop::book-details
  - text: The field asks for a language tag such as en-US or pt-BR, and the language is not used until it is one
    kind: condition
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Language
    contexts:
      desktop:
        place: desktop::book-details
---

# A language that is not a language tag

## Trigger

What was typed is not a language tag.

## Outcome

The books keep the language of the conversion options until a valid tag is typed; a tag in any capitalization is written in its standard form.
