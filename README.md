# greenlight-extension-updates

Public HTTPS host (GitHub Pages) for the Greenlight Authenticator browser
extension's enterprise force-install artifacts.

- Base URL: `https://gdoemling.github.io/greenlight-extension-updates/`
- `update.xml` — Chromium update manifest, pinned extension ID `jhigacbofegfkfdbkghaindcigehdkkf`
- `greenlight-authenticator-chrome.crx` — signed with the pinned key.
  with the pinned key (`tools/extension-key.private.pem`, kept offline). Signing
  with any other key changes the extension ID and breaks force-install and the
  desktop native-messaging bridge.

To publish a new version: build the signed `.crx`, regenerate `update.xml`
(`node scripts/generate-enterprise-policy.js --base-url https://gdoemling.github.io/greenlight-extension-updates/`
in the main repo), commit both here, then verify with
`npm run policy:verify-hosting -- --base-url https://gdoemling.github.io/greenlight-extension-updates/`.
