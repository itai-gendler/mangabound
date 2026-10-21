---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User turns off Tell me when a long conversion ends and Keep the computer awake while converting
    kind: actor
    actor: user
    entities:
      - entity: app-settings
        effect: changes
        facts:
          - Tell me when a long conversion ends
          - Keep the computer awake while converting
    contexts:
      desktop:
        place: desktop::app-settings
---

# Turn off the notification and keeping awake

## Trigger

The User does not want the system to be held awake or notified.

## Outcome

From the next Process, the computer may sleep during a conversion and its end is not announced.
