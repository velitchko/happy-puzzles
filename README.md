# Happy Puzzles 🧩

A print-and-play card game toolkit for exploring how people communicate, interpret, and construct abstract tasks. The goal of the game is to be hands-on and use puzzle pieces as a shared physical language.

## What is it?

Happy Puzzles is a game where players work with a deck of task cards and a set of physical puzzle pieces. Each card presents an analysis or reasoning task. Players use puzzle pieces to represent, communicate, and reconstruct those tasks without using words. The objective is to arrive to an arrangment of puzzle pieces that also makes sense and can be de-constructed by other players. 

The game is designed to surface how differently people understand the same task, how meaning shifts when passed between people, and how breaking a task into components changes the way we think about it.

## Card Deck

The deck is generated from a CSV file of tasks and printed double-sided:

- **Front** — the task text, large and readable
- **Back** — a unique cute puzzle character in a random colour, identical across all cards so backs don't reveal which task is which

Cards are sized to standard poker card dimensions (≈ 63.5 × 88.9 mm), 9 per A4 sheet.

## Printing

You need to start a web server to generate the set of cards (since a .csv file is being loaded).

We recomment quickly running `python -m http.server` (if you do not have python installed just look for alternatives or local server setups).


Open `index.html` in a browser and use **File → Print** (Ctrl+P) with these settings:

| Setting | Value |
|---|---|
| Paper size | A4 |
| Scale | 100% (not "fit to page") |
| Margins | None |
| Pages per sheet | 1 |
| Two-sided | Flip on long edge |
| Color mode | **Color** |
| Print backgrounds | ✅ On |
| Headers and footers | ❌ Off |

The sheet contains registration marks (`+` crosshairs) at the four corners of the card grid. Hold a printed sheet up to a light after printing to verify front/back alignment. If using a professional print service, export fronts and backs as separate PDFs and let them handle registration.

## Files

| File | Purpose |
|---|---|
| `index.html` | Card generator: open in browser to preview and print |
| `tasks.csv` | Task list: one task per row, edit to change card content |
| `puzzle.svg` | Source puzzle character artwork |

## Customising Tasks

Edit `tasks.csv`: the first row is a header and is skipped. Add or remove rows freely; the layout automatically adjusts the number of sheets.

## Tech

Pure HTML + CSS + JavaScript. Uses [D3.js](https://d3js.org) only for CSV loading. No build step, no dependencies to install — just open the file.
