---
appliesTo:
  - type: capability
    id: choose-book-cover
  - type: capability
    id: add-covers-from-folder
references:
  - kind: code
    role: implementation
    target: src/domain/book-covers.ts#looksLikeCoverImage
---

# A cover is a JPEG, PNG, WebP, GIF or BMP image

A file is taken as a cover only if what it holds is one of those images, whatever its name says; a damaged file, or one that only has an image's name, is not used and the page says so.
