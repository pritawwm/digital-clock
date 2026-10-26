# Digital Clock

A minimal seven-segment digital clock that runs in the browser and installs as an app on desktop and mobile. It shows the time in 24-hour format with hours, minutes and seconds.

## Features

- Clean seven-segment display with a soft fade between digits
- Fullscreen mode that fits phones, tablets and desktops, in portrait and landscape (portrait stacks hours, minutes and seconds in rows)
- Installable as an app, with its own icon and window
- Works offline after the first visit
- Keeps the screen awake while the app is open, and stops when the battery is at 20% or below and not charging
- Respects the system "reduce motion" setting

## Install

Open the live site, then:

- **Windows or Mac (Chrome or Edge):** click the install icon in the address bar, or use the menu and choose "Install Digital Clock".
- **Android (Chrome):** open the menu and choose "Install app" or "Add to Home screen".
- **iPhone or iPad (Safari):** tap Share, then "Add to Home Screen".

Open the app once while online so it can save its offline copy.

## Privacy

The clock collects nothing. It has no analytics, no tracking and no network requests, and its security policy blocks connections to other sites. The only thing saved on your device is a copy of the app's own files, so it can work offline.

## Notes on keep-awake

- The screen stays on only while the app is visible, and is requested again when you return to it.
- The 20% battery rule needs a browser that reports battery level (Chrome and Edge do). On browsers that don't, such as Safari, the system's own power-saving behavior applies.
- If a browser refuses the request, the clock tries again on your next tap or key press.

## Project files

| File | Purpose |
| --- | --- |
| `index.html` | The clock: page, styles and script in one file |
| `manifest.webmanifest` | App name, colors and icons for installing |
| `sw.js` | Saves the app's files for offline use |
| `icons/` | App icons |

## Updating

The page's security policy locks its inline style and script to specific SHA-256 hashes. If you edit anything inside the `<style>` or `<script>` blocks of `index.html`, you must recalculate both hashes and update the policy at the top of the file, or the page will load blank.

After changing any app file, raise the version number at the top of `sw.js` (for example `digital-clock-v2` to `digital-clock-v3`) so devices replace their saved copy.

## License

Released under the [MIT License](LICENSE).
