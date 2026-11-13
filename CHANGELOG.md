# Changelog

## [0.7.3] — 2026-11-13

- Added an expandable **Comandi avanzati Kodi** panel inside **Gesture e controlli extra**.
- 77 contextual action shortcuts in six categories: diagnostics, playback, video, audio/subtitles, PVR and navigation.
- Added a custom Kodi Action ID input and a JSON-RPC method/JSON parameters input.
- Uses existing Home Assistant `kodi.call_method` integration; no Kodi Bridge backend changes required.
- Certain actions are context dependent and require Kodi/player support; advanced JSON-RPC can change Kodi state.

## [0.5.4] — 2026-10-28

- Modern Media Remote visual refresh: bundled vector icons, color-coded media controls and mode buttons.
- Kept existing Kodi remote, media browser, playback and service-call behavior.
- Initial HACS/Marketplace-ready distribution packaging; JavaScript content unchanged from the tested v0.5.4 card.
