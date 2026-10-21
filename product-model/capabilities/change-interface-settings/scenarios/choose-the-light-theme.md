---
kind: alternate
routes:
  desktop: Desktop
steps:
  - text: The User chooses Light (paper) as the theme
    kind: actor
    actor: user
    entities:
      - entity: app-settings
        effect: changes
        facts:
          - Theme
    contexts:
      desktop:
        place: desktop::app-settings
---

# Choose the light theme

## Trigger

The User works in a bright room.

## Outcome

The window, its title bar included, is light at once, and no longer follows the system until Automatic is chosen again.
