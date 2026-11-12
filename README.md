# Kana Software releases

Installers for Kana Software's Windows apps. Each release is tagged `<app>-v<version>`, such as `calculator-v0.16.0`. Download the `-setup.exe` from an app's newest release.

Installed apps update themselves from About, using the feed at `<app>/latest.json`. The installers aren't code signed, so Windows SmartScreen may warn about them the first time: choose More info, then Run anyway.

Releases are published here by each app's release workflow. Don't edit or delete them by hand.

## How releases are made

Running `pnpm release` in an app's repo tags the app's commit and starts this repo's Release workflow, which checks the app out, builds and signs the installer, and publishes it here. App repos are private, so the secrets every app's release needs live in this repo:

- `TAURI_SIGNING_PRIVATE_KEY` and `TAURI_SIGNING_PRIVATE_KEY_PASSWORD`: the updater signing key.
- `KANA_SOURCE_TOKEN`: a fine-grained token, owned by kana-software, with read access to the contents of all its repositories.
