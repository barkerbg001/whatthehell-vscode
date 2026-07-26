# Changelog

All notable changes to the "What the Hell" theme are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/).

## [1.1.2] - 2026-07-26

### Added

- `.github/workflows/release.yml` — pushing a `v*` tag now packages the extension and publishes a GitHub Release with the `.vsix` attached.
- A "Releasing" section in `CONTRIBUTING.md`.

### Changed

- Bumped the `engines.vscode` minimum from `^1.18.0` to `^1.96.0` — the old floor dated back to 2017, long before the Chat/Copilot color keys this theme now styles existed.
- README: fixed the "Releases" install method to reflect an actual Release now being published there; replaced the duplicated Contributing/Publishing sections with a link to `CONTRIBUTING.md`; added Changelog/Releases links.

## [1.1.1] - 2026-07-26

### Added

- `CONTRIBUTING.md`.

## [1.1.0] - 2026-07-26

### Added

- `.vscodeignore` so packaging (design source files, CI config, tooling config) no longer ships inside the `.vsix`.
- `CHANGELOG.md` and `TODO.md`.
- `"license": "MIT"` in `package.json`.
- `"scripts"` in `package.json`: `format`, `lint`, `validate-theme`, `package`, `publish`.
- `.vscode/launch.json` so `F5` opens an Extension Development Host with the theme loaded.
- Color coverage for ghost text (inline completions), the Chat view, the Inline Chat widget, inline chat diffs, and interactive/panel chat — these previously fell back to VS Code's defaults.

### Changed

- Fixed the stale `homepage` URL in `package.json` (`master` → `main`).
- Optimized `images/logo.png` (1.3MB → 467KB, same dimensions and visual quality).
- Simplified `package.json` devDependencies down to just `prettier` and `vsce`.

### Removed

- Removed the Marketplace badges, the Preview screenshot, and the color palette tables from the README.
- Deleted the unused `images/logo.sketch` and `images/demo.png` (still recoverable from git history).

### CI

- CI now uses `npm run package` instead of installing `vsce` globally.
- Added a `Lint` step and a `Validate theme JSON` step before packaging.

## [1.0.7] - 2025-08-12

### Changed

- Repositioned the theme's description from "chaotic... mismatched... erratic" to "sleek, high-contrast... clearly defined" in `package.json` and the README.

### Removed

- Removed the demo screenshot from the README.

### Maintenance

- Routine devDependency updates (`@babel/core`, `@babel/eslint-parser`, `eslint`, `eslint-config-prettier`, `prettier`).

## [1.0.6] - 2024-07-27

### Maintenance

- Version bump; no functional changes.

## [1.0.3] - 2024-07-26

### Changed

- Updated GitHub Actions workflow to `actions/*@v3`.

## [1.0.2] - 2024-07-26

### Fixed

- Corrected the repository URL in `package.json` (pointed at the renamed `whatthehell-vscode` repo instead of the old `WhatTheHell` name).

## [1.0.1] - 2024-07-26

### Added

- Initial release: color theme definition, README, license, and packaging config.

### Changed

- Tuned the color palette.
- Reduced the demo image file size.
