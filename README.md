# Ledger — a task list app

A minimal, ledger-styled to-do app built with plain HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies beyond a couple of Google Fonts.

![Type](https://img.shields.io/badge/type-standalone%20HTML-informational)
![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

## Features

- Add tasks by typing and hitting **Enter** or clicking **Add**
- Mark tasks as settled (complete) or open with a single tap
- Delete individual tasks
- Filter view: **all** / **open** / **settled**
- Bulk-clear all settled tasks at once
- Live tally of open vs. settled entries
- Data persists locally in your browser via `localStorage` — refresh or close the tab and your tasks are still there
- Fully responsive, accessible (visible keyboard focus states, screen-reader labels, respects reduced-motion preference)

## Demo

Open `todo-ledger-standalone.html` in any browser — no setup, no server, no build step.

## Getting started

### Option 1: Just open it
1. Download `todo-ledger-standalone.html`
2. Double-click it to open in your default browser
3. Start adding tasks

### Option 2: Serve it locally (optional)
If you'd rather run it through a local server instead of the `file://` protocol:

```bash
# Python 3
python3 -m http.server 8000

# Node (with npx)
npx serve .
```

Then visit `http://localhost:8000/todo-ledger-standalone.html`.

## Tech stack

| Layer      | Choice                                      |
|------------|----------------------------------------------|
| Markup     | Semantic HTML5                               |
| Styling    | Vanilla CSS (custom properties, no framework) |
| Logic      | Vanilla JavaScript (ES6+, no libraries)       |
| Fonts      | Fraunces, Inter, IBM Plex Mono (Google Fonts) |
| Storage    | Browser `localStorage`                       |

## Project structure

```
.
├── todo-ledger-standalone.html   # everything: markup, styles, and logic in one file
└── README.md                     # this file
```

## How data storage works

- Tasks are saved as a JSON array under the `localStorage` key `ledger-tasks`.
- Storage is scoped **per browser, per origin** — opening the file in a different browser, or moving/renaming it in a way that changes its origin, starts a fresh, empty list.
- Clearing your browser's site data or cache for local files will erase saved tasks.
- There is no backend, account system, or cloud sync — everything stays on your machine.

## Customization

Since it's a single file, tweaks are straightforward:

- **Colors**: edit the CSS custom properties at the top of the `<style>` block (`--paper`, `--ink`, `--accent`, `--moss`, `--brick`, etc.)
- **Fonts**: swap the Google Fonts `<link>` in `<head>` and update the relevant `font-family` declarations
- **Task limit**: adjust the `maxlength` attribute on the text input
- **Storage key**: change the `STORAGE_KEY` constant in the script if you want to run multiple independent instances in the same browser

## Browser support

Works in any modern browser with `localStorage` support (Chrome, Firefox, Safari, Edge). No support for Internet Explorer.

## Known limitations

- No sync across devices or browsers
- No due dates, priorities, or categories (by design — kept intentionally minimal)
- No undo after deleting a task

## License

MIT — free to use, modify, and distribute for personal or commercial projects.
