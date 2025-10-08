# Connect Four — Browser implementation

A small, single-file (HTML + CSS + JS) Connect Four game you can open in a browser. It includes keyboard controls, theme toggling, undo/redo history (optional), and a persistent scoreboard saved to localStorage.

## Features

- Playable 7×6 Connect Four board (6 rows × 7 columns).
- Keyboard controls: Left/Right to select column, Enter to drop.
- Click/tap controls: drop buttons above the board for each column.
- Theme toggle (Light / Dark) — selection persists between visits.
- Optional move history (enable to use Undo / Redo).
- Persistent scoreboard stored in localStorage (wins per player).
- Responsive, modern UI with accessible roles and labels.

## Files

- `index.html` — main app (HTML, JavaScript bootstrapped in-page).
- `board.css` — styling and themes.
- `README.md` — this file.

## Run locally

This is a static site — just open `index.html` directly, or run a tiny local server (recommended to avoid file:// restrictions):

```bash
# from the project root
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## Controls

- Mouse / touch: click a column's Drop button to place a disc.
- Keyboard:
  - Left / Right: move the column focus
  - Enter: drop a disc into the focused column
  - Use the "Enable history" toggle to allow Undo (Ctrl+Z-like) and Redo.

## Persistence & Keys

- Theme is stored in localStorage key: `cf_theme` (`"light"` or `"dark"`).
- Scores are stored in localStorage key: `cf_scores_v1` (JSON object `{ "1": <wins>, "2": <wins> }`).

## Developer notes

- The game logic is implemented in an ES6 class in `index.html` (`ConnectFour`).
- The board is rendered as a CSS grid; the script dynamically creates the grid cells and the per-column drop controls.
- History (undo/redo) uses a simple JSON snapshot queue — it's intentionally lightweight and bounded.
