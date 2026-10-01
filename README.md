# io.github.deterous.redumper-gui
Unofficial Flatpak packaging for Redumper-GUI, a graphical interface for dumping optical discs. Upstream application by Deterous.

## Automation

- `.github/workflows/update-redumper-gui.yml` runs weekly (and on manual dispatch) to check for new upstream Redumper-GUI releases, regenerate `cargo-sources.json`, update the manifest and MetaInfo, and open a pull request with the changes.
- `.github/workflows/build-flatpak.yml` builds the Flatpak with `flatpak-builder` whenever the manifest, MetaInfo, desktop file, or `cargo-sources.json` change (on pull requests for validation, and on pushes to `main` for publishing). On `main`, it also creates a GitHub Release tagged from the MetaInfo `<release version="…">` entry and attaches the built `.flatpak` bundle as a release asset.
