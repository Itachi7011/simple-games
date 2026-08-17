# Simple Games

**A small collection of self-contained single-file browser games — no build step, no dependencies, one HTML file per game.**

![HTML5](https://img.shields.io/badge/HTML-5-e34c26)
![CSS3](https://img.shields.io/badge/CSS-3-1572B6)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-f7df1e)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## Table of Contents

- [Why This Project Exists](#why-this-project-exists)
- [Games](#games)
- [Screenshots](#screenshots)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Local Development](#local-development)
- [Environment Variables](#environment-variables)
- [Known Issues](#known-issues)
- [Testing](#testing)
- [Security](#security)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Why This Project Exists

Small browser games are a good way to practice core JavaScript game-loop concepts (animation frames, collision detection, state management) without any framework or build tooling overhead. This repository collects a handful of these as fully self-contained, single-file games.

## Games

Each game is a single, standalone `index.html` file — open it directly in a browser, no server or build step required.

| Game | Folder | Rendering | Description |
|---|---|---|---|
| Rotating Circle Physics Game | `Ball game/` | DOM + CSS (no `<canvas>`) | Balls bounce inside a rotating circular boundary with a gap to escape through; DOM-element-based physics and collision detection rather than canvas rendering. |
| Color Switch (Enhanced) | `Color Switch Game (boring)/` | Canvas 2D | A color-matching arcade game — pass through obstacles that match your current color. |
| Flappy Space (Easier Mode) | `Flappy Space Game/` | Canvas 2D | A Flappy-Bird-style side-scroller with a space theme, tuned for easier difficulty per its title. |
| Stack Jump 3D (Dynamic Edition) | `Stack  Jump 3d Game (boring)/` | Canvas 2D (pseudo-3D via projection, not a WebGL/Three.js scene) | A stacking/jumping arcade game with a 3D-styled visual presentation drawn on a 2D canvas. |

The parenthetical suffixes ("boring") in two folder names are the author's own informal naming and are preserved as-is rather than silently renamed, since the goal of this audit was not to change project content — see [Known Issues](#known-issues) for a naming-cleanup recommendation.

## Screenshots

> _RECOMMENDED ADDITION — screenshots are not yet part of the repository. See [Visual Presentation](#visual-presentation-guide) below for exactly what to capture, one per game._

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 (one file per game) |
| Styling | Inline `<style>` per game file |
| Behavior | Vanilla JavaScript (inline `<script>` per game file); Canvas 2D API for 3 of 4 games, DOM/CSS-based physics for 1 |

No framework, no build tool, and no shared code between games — each `index.html` is fully self-contained.

## Project Structure

```
simple-games/
├── Ball game/
│   └── index.html                       # Rotating Circle Physics Game (DOM/CSS-based)
├── Color Switch Game (boring)/
│   └── index.html                        # Color Switch - Enhanced (Canvas 2D)
├── Flappy Space Game/
│   └── index.html                         # Flappy Space - Easier Mode (Canvas 2D)
└── Stack  Jump 3d Game (boring)/
    └── index.html                          # Stack Jump 3D – Dynamic Edition (Canvas 2D)
```

## Installation

No build tooling or dependencies are required. Each game can be opened directly:

```bash
git clone https://github.com/Itachi7011/simple-games.git
cd simple-games
```

## Local Development

Since each game is a single self-contained HTML file with no `fetch()` calls to other local files, you can open any game's `index.html` directly in a browser (`file://`) — no local server is required, unlike the other repositories in this author's portfolio that share components across pages.

```bash
open "Ball game/index.html"
# or serve the whole folder if you prefer a consistent workflow across repos:
python3 -m http.server 8000
```

## Environment Variables

None. These are entirely client-side games with no backend and no build-time configuration.

## Known Issues

- **Folder names contain spaces, and two contain double spaces** (`Stack  Jump 3d Game (boring)` has two spaces between "Stack" and "Jump"). This works fine for direct browser access but is fragile if ever deployed as a linked, URL-addressable site (spaces need encoding, double spaces are easy to mistype). RECOMMENDED: rename folders to kebab-case (e.g. `rotating-circle-physics/`, `color-switch/`, `flappy-space/`, `stack-jump-3d/`) if this collection is ever given a shared landing page/index.
- **No shared landing page.** There is currently no `index.html` at the repository root linking to the four games — a visitor (or GitHub Pages deployment) has no single entry point. RECOMMENDED ADDITION: a simple root `index.html` listing and linking to all four games, if this repo is meant to be browsable as a deployed site rather than just cloned and opened locally.
- **The "(boring)" naming** on two folders is informal/developer shorthand kept from the original commit; consider renaming for a more polished public-facing repo.

## Testing

No automated test suite currently exists, and none is strongly recommended here given the small, purely-visual, single-file nature of each game — RECOMMENDED ADDITION (optional): basic HTML validation via the included CI workflow.

## Security

These are static, client-side games with no backend, no authentication, and no data collection.

## Roadmap

See [`docs/development.md`](docs/development.md) for suggested next steps, including the shared landing page mentioned above.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## License

Released under the [MIT License](LICENSE).
