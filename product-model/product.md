---
id: mangabound
summary: Organize manga chapters into volumes, convert them into EPUB, CBZ or PDF books for an e-reader, then save them or share them with KOReader over the local network.
category: media
tags:
  - manga
  - e-reader
  - ebook-conversion
  - opds
  - desktop-app
authors:
  - name: gustavommcv
    url: https://github.com/gustavommcv
license: MIT
languages:
  - en
  - pt-BR
limitations:
  - 'Mangabound works only with manga a person already has: it neither downloads chapters nor shows their pages.'
  - Online sources supply volume and author data only; manga pages never leave the computer.
  - Ready books wait on this computer until they are saved or deleted, and are not a backup.
  - Books are shared only on the local network interface the person chooses, and only while Mangabound is open.
  - 'A newer version is only announced: the person downloads and installs each release.'
references:
  - kind: doc
    role: intent
    target: README.md
  - kind: doc
    role: context
    target: docs/architecture.md
  - kind: adr
    role: intent
    target: docs/adr/0005-product-boundaries-and-anti-goals.md
  - kind: doc
    role: intent
    target: website/src/content/docs/getting-started/overview.mdx
  - kind: doc
    role: context
    target: docs/adr/README.md
---

# Mangabound

Mangabound is a desktop app that turns a person's manga chapter folders, libraries of manga folders and CBZ files into books for an e-reader. It groups chapters into volumes with the bundled mangabind, converts them with the bundled mangapress for a chosen device and format, keeps the finished books until they are saved, and can serve them to KOReader as an OPDS catalog on the local network. The model complements the project's architecture overview, its architecture decision records and the user guide, and uses their words; the decision records keep the reasons, the model keeps what the product does.

## Intent

In the README's words: "Mangabound is a desktop app for organizing manga chapters into volumes and converting them into books for your e-reader. Choose how chapters are grouped and fine-tune page size, margins, and image quality for your device. Once processed, save your books locally or share them directly with KOReader over your local network."

ADR 0005 draws the line: "Mangabound is a capable workflow application, not a general manga platform."
