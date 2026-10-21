---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User chooses 6 under Parallel conversions on a computer of many processor threads
    kind: actor
    actor: user
    entities:
      - entity: app-settings
        effect: changes
        facts:
          - Parallel conversions
    contexts:
      desktop:
        place: desktop::app-settings
  - text: The App settings keep the choice; a queue already running keeps the one it began with
    kind: condition
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Parallel conversions
    contexts:
      desktop:
        place: desktop::app-settings
---

# Convert more books at once

## Trigger

The computer has processors to spare during long conversions.

## Outcome

From the next Process, up to six books of one title are converted at once; a number kept on a bigger computer is lowered to what this one can be asked for.
