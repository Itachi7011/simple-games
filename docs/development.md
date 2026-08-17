# Development Guide

## Prerequisites

None beyond a modern web browser. No Node.js, package manager, or build tool is required — each game opens directly via `file://`.

## Running Locally

```bash
git clone https://github.com/Itachi7011/simple-games.git
cd simple-games
open "Ball game/index.html"   # or double-click it in a file browser
```

## Suggested Next Steps

In rough priority order:

1. **Add a root `index.html` landing page** linking to all four games with a short description and (once added) a screenshot/thumbnail each — this is the main thing standing between this repo and being directly deployable/browsable as a single site (e.g. via GitHub Pages), rather than something that has to be cloned and opened file-by-file.
2. **Rename folders to kebab-case** (`rotating-circle-physics/`, `color-switch/`, `flappy-space/`, `stack-jump-3d/`) if a landing page/deployment is added, since spaces in folder names complicate URL-based linking.
3. **Add new games** following the existing single-file, no-dependency pattern (see [CONTRIBUTING.md](../CONTRIBUTING.md#adding-a-new-game)).

## Project Conventions

- **One folder per game, one `index.html` per folder**, fully self-contained (inline `<style>` and `<script>`, no external JS/CSS files, no CDN dependencies observed in the current four games).
- Keep new games consistent with this pattern unless a shared landing page/build step is introduced deliberately.

## Before Opening a Pull Request

- Open the game directly via `file://` to confirm it doesn't rely on anything requiring a server.
- Test on both desktop and touch (mobile) input if the game supports touch controls.
