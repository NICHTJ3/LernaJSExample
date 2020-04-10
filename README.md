# Lerna JS Example
[Lerna](https://lerna.js.org/) is a tool that optimizes the workflow around
managing multi-package repositories with git and npm.

## Quick getting started
```sh
# Install dependencies
npx lerna bootstrap
# Run api's (Note: There is less output than expected with this command)
# You can run 'npx lerna exec npm run dev' instead for more output
npx lerna run dev
```
__Note__: API's will be available on ports:
- 5000
- 5001

## Available commands
- npx lerna bootstrap
  - Bootstrap the packages in the current Lerna repo. Installing all their
    dependencies and linking any cross-dependencies.
- npx lerna import <pathToRepo>
  - Import the package in the local path <pathToRepo>
    into packages/<directory-name> with commit history.
- npx lerna publish
  - Create a new release of the packages that have been updated.
    Prompts for a new version and updates all the packages on git and npm.
    - Options
      - --npm-tag [tagname] — Publish to npm with the given npm dist-tag (Defaults to latest).
      - --canary/-c – Create a canary release.
      - --skip-git – Don't run any git commands.
      - --force-publish [packages] — Force publish for the specified packages
        (comma-separated) or all packages using * (skips the git diff check
        for changed packages).
- npx lerna changed
  - Check which packages have changed since the last release.
- npx lerna diff [package?]
  - Diff all packages or a single package since the last release.
- npx lerna run [script]
  - Run an npm script in each package that contains that script.
- npx lerna ls
  - List all of the public packages in the current Lerna repo.
