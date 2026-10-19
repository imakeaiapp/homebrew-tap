# imakeaiapp/homebrew-tap

Official Homebrew tap for [iMake](https://imake.lol/).

## Install

```bash
brew install imakeaiapp/tap/imake
```

Apple Silicon, macOS 14 or newer. The cask installs the signed and notarized
`iMake.app` published to `https://downloads.imake.lol`.

## Uninstall

```bash
brew uninstall --cask imake
```

That removes the app and unloads the background `com.devcluster.*` agents. Add
`--zap` to also delete `~/.devcluster` and the app's caches, logs, and
preferences.

## Updates

The app updates itself, so Homebrew will not fight it: the cask is marked
`auto_updates true` and `brew upgrade` only replaces the bundle when the
published release is newer than the installed one.

`.github/workflows/update-cask.yml` polls
`https://downloads.imake.lol/releases/latest/macos.json` hourly and commits a
new version and `sha256` when a release ships. Run it by hand with
`gh workflow run update-cask.yml -R imakeaiapp/homebrew-tap`.
