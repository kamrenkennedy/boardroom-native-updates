# Boardroom — Mac updates

Sparkle update feed for the Boardroom Mac app. The app source is private. This repository holds only
`appcast.xml` and the notarized release zips (GitHub Releases), signed with Kam Studios' Sparkle key.

## Release flow

1. Bump `MARKETING_VERSION` and `CURRENT_PROJECT_VERSION` in boardroom-native `project.yml`.
2. Archive, export Developer ID, notarize and staple the app.
3. From `/tmp`: `zip -qrXy Boardroom-<version>.zip Boardroom.app`, then `sign_update` the zip.
4. Create a Release `v<version>` here with the zip, and add an `<item>` to `appcast.xml` (newest first).
5. Commit and push. Installed apps check hourly and update on quit.
