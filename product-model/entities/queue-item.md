---
domain: queue
relations:
  - entity: library-title
    verb: holds
    cardinality: one-to-many
  - entity: chapter-mapping
    verb: has
    cardinality: one-to-one
  - entity: book-cover
    verb: has
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#queueReducer
  - kind: code
    role: implementation
    target: src/domain/input-queue.ts#describeRow
  - kind: code
    role: implementation
    target: src/application/workflows/input-sessions.ts#InputSessions
  - kind: adr
    role: intent
    target: docs/adr/0010-input-queue.md
---

# Queue item

One row of the queue: a manga folder, a library of manga folders, or a CBZ file. It is read when it is added, and what it holds decides what a run does with it. Taking it out of the queue never touches its files; what it keeps for this session (its title and its own options) goes with it.

## Information kept

- **Kind** — a manga folder, a library (a folder of manga folders, known only once it is read) or a CBZ file
- **Name** — the folder's or file's name, shown on its row
- **Location** — where it is on this computer; the same location added again stays one item
- **Read problem** — why it could not be read, in the words of the tool or the system
- **Folders left out** — the folders of a manga whose names hold no chapter number: they are in no book
- **Links not followed** — the folders of a library that are links to a series kept elsewhere: they are not read
- **Title** — the Series title, or the Book title for an item made into one book; left empty, the name is used
- **Author** — who wrote it, typed or found online; a manga folder keeps it in its mangabind.json
- **Language** — the language tag of its EPUB books, such as pt-BR; a manga folder keeps it in its mangabind.json
- **Own options** — the conversion options it sets differently from the queue; kept only while the app is open

## States

### Checking

Just added: the folder is being read, or the file checked.

### Could not read

Reading failed; the row says why, and a run leaves it out.

### Read

Read as a manga folder, a library or a CBZ; whether a run can make books of it depends on its volumes and the steps.
