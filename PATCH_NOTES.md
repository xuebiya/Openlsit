# Local OpenList build notes

This fork embeds a locally rebuilt OpenList frontend in `public/dist`.

Frontend behavior changes included in that dist:

- Mobile toolbar hides ArtPlayer web-fullscreen (`fullscreenWeb`) and keeps native fullscreen.
- Mobile progress touch area is reduced and ignores toolbar controls, preventing fullscreen taps from being treated as progress seeks.
- DPlayer-style seeking remains: dragging previews only; one real seek is sent on release.
- Mobile video-surface horizontal gesture seeking is preserved.

GitHub Actions workflow `.github/workflows/build-all-embedded-dist.yml` builds binaries with `USE_EMBEDDED_WEB=1`, so `build.sh` uses the committed `public/dist` instead of downloading official frontend assets.
