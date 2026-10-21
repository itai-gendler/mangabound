---
appliesTo:
  - type: capability
    id: confirm-chapter-mapping
  - type: capability
    id: assign-chapters
references:
  - kind: code
    role: implementation
    target: src/domain/mapping.ts#validateMapping
  - kind: doc
    role: intent
    target: website/src/content/docs/user-guide/mapping-editor.mdx
---

# A chapter that is in the folder more than once is in no book

mangabind cannot choose between two copies of a chapter, such as Ch.0002 [G1] and Ch.0002 [G2], so it leaves every copy out; placing one of them in a volume changes nothing. The editor lists it as an error until all but one copy are removed from the folder and the folder is added again.
