---
appliesTo:
  - type: capability
    id: edit-item-options
  - type: capability
    id: use-queue-options
  - type: capability-scenario
    id: reset-the-options-page
  - type: entity
    id: queue-item
    facts:
      - Own options
references:
  - kind: code
    role: implementation
    target: src/domain/item-options.ts#effectiveOptions
  - kind: code
    role: implementation
    target: src/domain/item-options.ts#withQueueValue
  - kind: adr
    role: intent
    target: docs/adr/0046-an-item-can-have-conversion-options-of-its-own.md
---

# An item follows the queue for every option it does not set

An item, or a library title, keeps only the options it sets differently; every other option is the queue's, including a change made to the queue later. Putting one of its options back puts it back to the queue's value, and putting the device back puts back the upscaling and color that device starts with. Reset to defaults on the queue's page leaves the items' own options alone. Own options last while the app is open and are not kept for the next launch, and they are not offered when a run only groups chapters.
