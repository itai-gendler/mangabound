---
appliesTo:
  - type: capability-scenario
    id: choose-a-device
  - type: capability
    id: reset-conversion-options
references:
  - kind: code
    role: implementation
    target: src/domain/output-profile.ts#withDeviceProfile
  - kind: adr
    role: intent
    target: docs/adr/0011-kcc-default-options.md
---

# Choosing a device also sets upscaling and color

Choosing a device puts enlarging small pages and keeping color back to where that device starts: on for most devices, off for older, low-resolution and Scribe readers and Other; color on only for color screens. Every other option stays. A device the bundled tools no longer list is replaced by one they do, with a notice.
