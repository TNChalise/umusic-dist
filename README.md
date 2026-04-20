# umusic-dist

Distribution manifest + release binaries for [uMusic](https://github.com/TNChalise/umusic) — a third-party YouTube Music iOS client.

This repo is intentionally minimal. The source code, issue tracker, and development history live in the main (private) repo. What's here:

- `apps.json` — AltStore / SideStore source manifest, auto-updated by CI on every `v*` tag push.
- GitHub Releases — hold the `.ipa` files that SideStore downloads and re-signs on each installer's device.

## Install

1. Install [SideStore](https://sidestore.io) on your iPhone and enable its VPN profile.
2. Inside SideStore → **Sources** → `+` → paste:
   ```
   https://tnchalise.github.io/umusic-dist/apps.json
   ```
3. Sign into SideStore with a free Apple ID (a dedicated sideload-only account is recommended).
4. Tap **Install** on the uMusic entry.

The app re-signs every 7 days automatically as long as SideStore has run in the background recently. Open SideStore every couple of weeks so iOS doesn't evict it.

## For operators

- `apps.json` is rewritten by `.github/workflows/release.yml` in the source repo each release; don't edit it by hand.
- Drop a 512×512 `icon.png` at the repo root to replace the SideStore placeholder icon.
