---
availability:
  - place: desktop
domain: queue
references:
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#queueReducer
  - kind: code
    role: implementation
    target: src/application/workflows/input-sessions.ts#InputSessions
---

# Remove an item from the queue

Takes one item out of the queue. Its files on disk stay as they were.
