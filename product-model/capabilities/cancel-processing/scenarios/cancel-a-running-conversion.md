---
kind: primary
routes:
  desktop: Desktop
steps:
  - text: The User cancels the conversion while a Queue item is being converted
    kind: actor
    actor: user
    entities:
      - entity: queue-item
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::processing
  - text: The Product stops the running tools and keeps the ready books already made in the Pending conversion
    kind: product
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Books
      - entity: ready-book
        effect: reads
        facts:
          - Name
    contexts:
      desktop:
        place: desktop::processing
  - text: The results show what was made; the items the run did not reach stay in the queue without being reported as left out
    kind: condition
    actor: user
    entities:
      - entity: pending-conversion
        effect: reads
        facts:
          - Item results
    contexts:
      desktop:
        place: desktop::results
---

# Cancel a running conversion

## Trigger

The User decides not to finish the run.

## Outcome

The run is over; the books it finished can be saved, and the unfinished items are still queued. A new run waits until stopping has finished.
