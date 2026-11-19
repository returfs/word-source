# Returfs Word source

Word is AGPL-3.0-only. The included SDK and shared external UI retain their MIT licenses. Third-party packages retain their own licenses.

This archive contains the Word source, templates, build configuration, locked dependency graphs, required shared source and the exact SuperDoc source revision e096323e7d5e54f95b4817d1d3aefde8c37d52cf (v1.46.3). No application data or repository history is included.

## Build Word

Use Node 24 and the pnpm version in internal/package.json. From internal/:

    pnpm install --frozen-lockfile
    pnpm --filter @returfs/extension-sdk build
    pnpm --filter word-editor build:federated

The remote is emitted in internal/extensions/word-editor/dist. For a standalone development view, run pnpm --filter word-editor dev. Account operations require a configured Returfs host; no credentials are included.

The versioned shared UI archive is the exact build consumed by Word. Its editable source is in external/extension-packages/shared-external-react. To rebuild it, install external/ with its frozen lockfile, run tsc and vite build in the shared package, then compile src/tailwind-entry.css with @tailwindcss/cli 4.3.3 and pack the same version. The language catalogues are included in src/state/Context; the sync script supports this standalone source tree.

SuperDoc source and its build instructions are in upstream/superdoc-1.46.3-source.tar.gz. The engine runtime is pinned to the published 1.46.3 package in the lockfile.

The source archive is published separately from runtime assets. Rebuild this offer whenever the delivered Word or shared source changes.

## Download

[Download the reviewed source archive](https://github.com/returfs/word-source/releases/download/word-1.0.0-2026-11-19/returfs-word-source.tar.gz).

SHA-256: `f06c8cbfc6d3d806a7d18dfdfa9e3fed453dd76966ca5022b70e0781f0456566`

The required source is the attached release archive. GitHub automatically generated repository archives contain only this README.
