# Traditions at Scott - Mongolian Grill — order tracker

A pixel-accurate static recreation of a campus order-tracking screen, built as a
personal design-emulation study. Single file, no build step, no dependencies.

## What's here

| File | Purpose |
|---|---|
| `index.html` | The whole app — markup, CSS and JS in one file |
| `manifest.json` | Web-app manifest (name, icons, standalone display) |
| `icon-180.png` | iOS home-screen icon |
| `icon-192.png` / `icon-512.png` | Android / browser icons |
| `icon-512-maskable.png` | Android adaptive icon (art inset to the 80% safe zone) |
| `favicon.ico`, `favicon-32.png` | Browser tab |

## Publishing

Push to a repo, then **Settings → Pages → Source: Deploy from a branch → `main` / root**.
It'll be live at `https://<user>.github.io/<repo>/` in a minute or two.

All asset paths are relative, so it works from a project subpath without changes.

## Add to home screen

Open the Pages URL **in Safari** on iOS (Chrome on iPhone can't do this), then
Share → Add to Home Screen. It launches without browser chrome, and the real iOS
status bar sits in the empty 56px strip at the top of the layout.

On Android, Chrome offers "Install app" from the ⋮ menu.

If you change an icon and iOS keeps showing the old one, delete the shortcut,
quit Safari, and re-add — or bump the filename (`icon-180-v2.png`) and update
the `href` in `index.html`.

## Notes on the build

Geometry was measured from 3× (1179×2556) screenshots and divided by 3, so every
value in the CSS is an exact CSS pixel. Text is positioned by measured **baseline**
rather than by padding: each element carries a `data-bl` attribute, and a small
script measures the loaded font's baseline offset and places it accordingly.

The board is a fixed 393×852 stage rendered 1:1 — it is deliberately *not* scaled
to fit the viewport, since scaling would break the pixel correspondence with the
reference screenshots. Short windows scroll instead.

`color-scheme: light` is forced, and every text node sets an explicit colour. This
is a light-mode-only recreation; without that, a dark-mode viewer flips the default
text colour to white and some strings vanish against the white background.

The gear at top right is a mockup control (order number, queue length, pickup time).
It is not part of the design being emulated — it lives in the status strip
specifically so the real nav bars stay untouched.

## Disclaimer

Unofficial and unaffiliated. This is a personal study of interface design, not a
functioning ordering app, and it is not endorsed by or connected to any company.
All trademarks and logos are the property of their respective owners.
