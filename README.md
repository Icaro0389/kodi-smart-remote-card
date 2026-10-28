# Kodi Smart Remote — Modern Media Remote

**Version 0.5.4** · A mobile-first Lovelace remote for Kodi with an integrated media browser, playback controls, colorful SVG icons, HDMI mode shortcuts and keyboard.

This repository packages the **exact JavaScript file tested on Home Assistant**. The distribution file is renamed only for compatibility with HACS; the JavaScript content is unchanged.

## Prerequisites

- Home Assistant with a working Kodi `media_player` entity and Kodi integration.
- [Kodi Smart Bridge integration](https://github.com/Icaro0389/kodi-smart-bridge-ha) if using TV/Radio/Movies/Series browser features, with its backend running and configured.
- The `shell_command` services for mode switching must exist if you use the Kodi/Moonlight/Retro/Off buttons. They are not installed by this card.

## Install via HACS (Dashboard)

1. In HACS, add `Icaro0389/kodi-smart-remote-card` as a **custom Dashboard** repository.
2. Install **Kodi Smart Remote**.
3. Check **Settings → Dashboards → Resources** and ensure the HACS-provided JavaScript module resource is present, or add it manually if HACS cannot manage resources.
4. **Important when migrating an existing manual installation:** remove/disable the previous resource `/local/kodi-smart-remote-v0.5.4.js?v=054` after confirming the HACS resource. Keep the original file for rollback, but load **one** version of the card at a time.
5. Reload the browser/dashboard.

The HACS resource URL is typically:

`/hacsfiles/kodi-smart-remote-card/kodi-smart-remote-card.js`

## Example Lovelace configuration

```yaml
type: custom:kodi-smart-remote
entity: media_player.192_168_178_88
mode_entity: sensor.modalita_hdmi
update_interval: 4
```

Adapt the entity IDs to your installation. No token is included in the Lovelace config; authentication to the bridge is handled by the Home Assistant custom integration.

## Manual install

Copy `dist/kodi-smart-remote-card.js` to `/config/www/kodi-smart-remote-card.js`, add a **JavaScript module** resource at `/local/kodi-smart-remote-card.js?v=054`, then reload the dashboard. Do not load two separate copies concurrently.

## Release and rollback

- Tag the initial GitHub release **`v0.5.4`** after uploading repository files.
- For an immediate rollback to the already-tested manual version, restore the single dashboard resource to `/local/kodi-smart-remote-v0.5.4.js?v=054` (as long as that file remains in `/config/www/`).
- No backend, Kodi, or Home Assistant Core restart is needed merely to switch the dashboard resource.

## Source and privacy

Single-file JavaScript without build dependencies. It is a frontend only: it does not contain IPTV provider credentials or bridge tokens. The example entity ID and mode entity ID are installation-specific and should be adapted in other homes.

**Current release scope:** This repository packages the already-working v0.5.4 card. It has not yet been tested through HACS installation; the existing manual installation remains the production fallback.
