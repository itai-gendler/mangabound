---
scope: 'The Mangabound desktop app and its OPDS catalog: the domain, application, adapters, library, OPDS, main-process and screen code under src/.'
method: Static reading of source, user guide, architecture overview and decision records; no code was run.
covered:
  - description: Queue, mapping, details, covers, options and run rules of the domain layer.
    paths:
      - src/domain/
  - description: Workflows that read inputs, plan, bind, convert and keep covers, preferences and app settings.
    paths:
      - src/application/
  - description: mangabind, mangapress, metadata provider, pending storage, cover, settings and sharing adapters.
    paths:
      - src/adapters/
  - description: Library catalog, pending saves and unique book names.
    paths:
      - src/library/
  - description: OPDS feeds and links.
    paths:
      - src/opds/
  - description: Main-process commands, closing, keeping awake, queue notices, diagnostics and tool checks.
    paths:
      - src/main/
  - description: Validated command contracts between the window and the main process.
    paths:
      - src/shared/
      - src/preload/
  - description: Screens, workflow state and feature components of the window.
    paths:
      - src/renderer/workflow-app.tsx
      - src/renderer/screens/
      - src/renderer/components/mapping/
      - src/renderer/components/details/
      - src/renderer/components/queue/
      - src/renderer/components/settings/
      - src/renderer/components/sharing/
      - src/renderer/hooks/
      - src/renderer/lib/
  - description: Message catalogs, read for the labels the model names.
    paths:
      - src/i18n/
exclusions:
  - description: Design system, shell and theme styling of the window.
    paths:
      - src/renderer/components/ui/
      - src/renderer/components/shared/
      - src/renderer/components/shell/
      - src/renderer/styles.css
      - src/renderer/assets/
      - src/renderer/stories/
  - description: Tests, fixtures, Storybook and visual baselines.
    paths:
      - tests/
      - .storybook/
  - description: Documentation site, contributor docs and release notes.
    paths:
      - website/
      - docs/
  - description: Build, packaging, toolchain pinning, lint rules, CI and release scripts.
    paths:
      - scripts/
      - packaging/
      - eslint-rules/
      - schemas/
      - .github/
      - forge.config.ts
      - toolchain.lock.json
  - description: Brand and icon assets.
    paths:
      - assets/
unmapped:
  - description: Window size and position kept between launches.
    paths:
      - src/main/window-state.ts
      - src/domain/window-state.ts
      - src/adapters/settings/fs-window-state-store.ts
  - description: About tab links, the data and logs folders, and the log file.
    paths:
      - src/main/project-links.ts
      - src/main/ipc/project-links.ts
      - src/main/log.ts
      - src/adapters/log/
  - description: Moving data from earlier storage places and clearing leftover scratch folders.
    paths:
      - src/adapters/library/legacy-storage.ts
      - src/adapters/fs/stale-scratch.ts
  - description: Which mangapress options another choice dims, option by option.
    paths:
      - src/domain/output-profile.ts
      - src/renderer/components/settings/mangapress-settings.tsx
  - description: Keyboard shortcut that opens the app settings.
    paths:
      - src/renderer/lib/shortcuts.ts
limitations:
  - description: Page processing and the warnings it raises happen inside the bundled mangabind and mangapress binaries, which are not in this repository.
    paths:
      - src/adapters/mangabind/
      - src/adapters/mangapress/
---

# Coverage
