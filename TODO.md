# TODO

Tracking the repo audit findings from 2026-07-26.

## ✅ Completed

- [x] Removed the redundant color-swatch column from the README color tables, keeping Hex + Usage.
- [x] Removed the duplicate `.vsix` line from `.gitignore` (`*.vsix` already covers it).
- [x] Added `.vscodeignore` — `.vsix` package trimmed from 11 files down to the 6 actually needed at runtime (dropped `.github/`, `.gitignore`, `prettier.config.js`, `images/logo.sketch`, `images/demo.png`).
- [x] Added `CHANGELOG.md`, reconstructed from git history (1.0.1 → 1.0.7 + Unreleased), so the Marketplace "Changelog" tab has content.
- [x] Added `"license": "MIT"` to `package.json`.
- [x] Fixed stale `homepage` URL in `package.json` — was pointing at `.../blob/master/README.md`, now `main`.
- [x] Deleted `images/logo.sketch` (unreferenced design source, still recoverable from git history if needed).
- [x] Removed the version/installs/downloads/license badges from the README.
- [x] Removed the Preview screenshot and the color palette tables from the README — the demo screenshot showed the actual chaotic theme, undercutting the "sleek/legit" listing copy.
- [x] Excluded `TODO.md` from the packaged `.vsix` (was shipping unintentionally — internal notes, not user-facing).
- [x] Confirmed with the repo owner: the odd hex values in `themes/whatthehell-color-theme.json` (`#123456`, `#654321`, `#abcdef`, `#fedcba`, `#321654`) are intentional, not placeholder bugs. No fix needed.
- [x] Deleted `images/demo.png` (unreferenced since the Preview section was removed from the README; still recoverable from git history).
- [x] Added theme coverage for AI/Copilot UI surfaces the theme previously left untouched: ghost text (inline completions), the Chat view, the Inline Chat widget, inline chat diffs, and interactive/panel chat — 30 new color keys, all reusing the existing palette.
- [x] Added `.vscode/launch.json` ("Run Extension" config) so `F5` opens an Extension Development Host with the theme loaded; excluded `.vscode/**` from the packaged `.vsix`.
- [x] Added `"scripts"` to `package.json`: `format` (prettier --write), `lint` (prettier --check), `package` (vsce package), `publish` (vsce publish).
- [x] Ran `npm run format` across the repo — `npm run lint` now passes clean on all files.
- [x] Updated `.github/workflows/main.yml` to use `npm run package` instead of `npm install -g vsce` — verified it builds the `.vsix` correctly with the pinned local `vsce`.
- [x] Added a `Lint` step to `.github/workflows/main.yml` (runs `npm run lint` before packaging) — verified it currently passes.
- [x] Dropped the unused eslint-related devDependencies (`eslint`, `eslint-config-prettier`, `@upstatement/eslint-config`, `@babel/core`, `@babel/eslint-parser`) — there's no real JS source in this repo for eslint to lint, just `prettier.config.js`. Verified `npm run lint` and `npm run package` still work after the cleanup.
- [x] Optimized `images/logo.png` with pngquant (256-color palette, quality 40-85): 1.3MB → 467KB (~64% smaller), same 1024×1024 dimensions, visually indistinguishable. Confirmed it still packages correctly.
- [x] Added a `validate-theme` script (`node -e "JSON.parse(...)"` on `themes/whatthehell-color-theme.json`) and a matching CI step before packaging. Verified it passes on the real file and fails loudly on broken JSON.
- [x] Tried adding an auto-bump `Bump version` step + re-enabling `Publish extension` in CI, but reverted both per repo owner's request (Azure DevOps PAT setup for `VSCE_PAT` turned out to be more hassle than wanted right now). CI is back to just lint → validate-theme → package → upload-artifact, no auto-publish.
- [x] Bumped to `1.1.0` (minor — real new functionality, the AI/Copilot color coverage, was added this session) and moved CHANGELOG's Unreleased section to a dated `[1.1.0]` entry. Packaged and verified.
- [x] Added `CONTRIBUTING.md` (setup, `npm run` scripts reference, PR steps). Confirmed it's excluded from the packaged `.vsix` by vsce's built-in defaults already.
- [x] Fixed the broken "download from Releases" install method (Method 3) — no GitHub Release had ever actually been published (zero git tags in history). Added `.github/workflows/release.yml`, triggered on `v*` tag pushes, that packages the extension and publishes a GitHub Release with the `.vsix` attached.
- [x] Rewrote the README: fixed Method 3 wording, replaced the duplicated Contributing/Publishing sections with a link to `CONTRIBUTING.md`, added Changelog/Releases links.
- [x] Bumped `engines.vscode` from `^1.18.0` (2017) to `^1.96.0` — roughly matches when the Chat/Copilot color keys added this session actually exist.
- [x] Bumped to `1.1.2` and cut the first real release (tagged `v1.1.2`, pushed to trigger the new release workflow).

## 🔲 Still to do

Nothing outstanding right now.
