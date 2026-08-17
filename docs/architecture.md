# Architecture

## Overview

This repository is a flat collection of independent, single-file games. There is no shared code, no server, and no build pipeline — each game's folder contains exactly one `index.html` with inline CSS and JavaScript.

## Per-Game Notes

- **Ball game/** (Rotating Circle Physics Game) — implemented without `<canvas>`; balls and the rotating boundary are DOM elements (`div`s) positioned and animated via JavaScript reading/writing CSS properties directly (transform/position), with collision detection computed against DOM element geometry rather than pixel/canvas data.
- **Color Switch Game (boring)/** — Canvas 2D (`getContext('2d')`), a single `<canvas id="gameCanvas">` with the full game loop, rendering, and collision logic in one inline script.
- **Flappy Space Game/** — Canvas 2D, same single-canvas single-script pattern.
- **Stack  Jump 3d Game (boring)/** — Canvas 2D; despite the "3D" in its name, it is drawn on a standard 2D canvas context using a pseudo-3D visual style (perspective-style shapes/shading), not a real 3D/WebGL scene (no Three.js or WebGL context is present).

## Why No Shared Code

Because each game is meant to be opened directly as a standalone file (`file://` works fine, no local server required — see [README: Local Development](../README.md#local-development)), sharing code across games would either require a build step (bundling) or `fetch()`-based includes (which, as seen in other repos in this author's portfolio, require serving over HTTP). Keeping each game fully self-contained is a deliberate simplicity trade-off, not an oversight.

## Hosting

No live deployment/hosting configuration exists for this repository at present — see [README: Known Issues](../README.md#known-issues) regarding the lack of a shared root landing page, which would be a prerequisite for a single combined deployment (e.g. GitHub Pages).
