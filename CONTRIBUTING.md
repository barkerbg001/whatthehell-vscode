# Contributing

Thanks for wanting to help out with **What the Hell**!

## Getting set up

1. Fork and clone the repo.
2. `npm install`
3. Press `F5` in VS Code to launch an Extension Development Host with the theme loaded (`.vscode/launch.json` handles this).
4. `Ctrl+K Ctrl+T` in the new window → select **What the Hell** to apply it.

## Making changes

- Theme colors live in `themes/whatthehell-color-theme.json`. See the [VS Code theme color reference](https://code.visualstudio.com/api/references/theme-color) for the full list of keys.
- Run `npm run validate-theme` after editing it to catch JSON syntax errors.
- Run `npm run format` before committing (this repo uses Prettier).
- Run `npm run lint` to check formatting without changing anything.
- Run `npm run package` to build a local `.vsix` you can install manually via **Extensions → ... → Install from VSIX**.

## Submitting a change

1. Create a feature branch (`git checkout -b feature/amazing-feature`)
2. Commit your changes (`git commit -m 'Add some amazing feature'`)
3. Push to the branch (`git push origin feature/amazing-feature`)
4. Open a Pull Request

## Reporting issues

Use the [issue tracker](https://github.com/barkerbg001/whatthehell-vscode/issues).

## Releasing (maintainers)

1. Bump the version: `npm version patch` (or `minor`/`major`), and update `CHANGELOG.md`.
2. Push the commit, then push the version tag: `git push && git push --tags`.
3. Pushing a `v*` tag triggers CI to package the extension and publish a GitHub Release with the `.vsix` attached.
4. To also publish to the Marketplace, run `npm run publish` locally (requires a `VSCE_PAT` environment variable — see [vsce's publishing docs](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)).
