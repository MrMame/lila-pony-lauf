# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

"Lila Pony Lauf" is a single-file browser endless-runner game: everything (HTML, CSS, JS) lives in `index.html`. There is no build step, no package manager, no dependencies, no tests, and no linter. To run it, open `index.html` in a browser (or serve the folder with any static server).

All user-facing text, comments, and identifiers in comments are **German** — keep new UI strings and comments in German to match.

## Architecture (inside `index.html`)

- **Fixed logical resolution**: the game simulates and draws in a 960×400 coordinate space (`W`, `H`, `GROUND`). `resize()` sizes the canvas to the CSS box × devicePixelRatio (capped at 2) and `draw()` applies `ctx.setTransform(scale, …)`, so all game code uses logical coordinates only. The `#wrap` container keeps the 960/400 aspect ratio; overlay cards use `cqw` container-query units so they scale with it.
- **State machine**: `state` is one of `menu | playing | paused | dying | gameover`. `update(dt)` branches on it; HTML overlays (`#menu`, `#over`) are toggled via the `hidden` class in `startGame` / `showMenu` / `showGameOver`. `dying` is a short physics-only animation before game over.
- **Main loop**: `requestAnimationFrame` → `update(dt)` (dt clamped to 33 ms) → `draw()`. Speed ramps from `START_SPEED` to `MAX_SPEED` over time; world objects move left by `speed * dt`.
- **Entities** are plain object arrays: `obstacles` (kinds `rock`, `fence`, `stump`, and `hang` — a hanging log you must duck under, only after `dist > 1200`), `enemies` ("Grummels", stompable; consecutive stomps without landing build `combo`, which resets on ground contact), `popels` (collectibles, +25), plus `particles` and `texts` for effects. `spawn()` / `spawnPopel()` control spawning and spacing based on distance-based `nextSpawn` and time-based `popelTimer`.
- **Collision**: AABB via `overlap()` against `playerBox()` (height depends on ducking). Obstacle hitboxes are shrunk slightly for fairness. A stomp counts when falling and the previous foot position (`player.prevBy`) was above the enemy's top + 14px.
- **Score** = `dist / 12 + bonus`; highscore persisted in `localStorage` under `lilaPonyHighscore` (wrapped in try/catch).
- **Rendering** is all procedural Canvas 2D (no images): each entity has its own `draw*` function; background parallax and decorations are deterministic via `hash(index)` so scrolling scenery is stable.
- **Audio** is synthesized with WebAudio oscillators via `tone()` / `sfx`; the AudioContext is created lazily on first sound. `M` toggles mute.
- **Input**: keyboard (Space/↑/W jump with jump buffer and variable height while held; ↓/S duck / fast-fall; P/Esc pause; M mute) and pointer/touch zones (left 60% of canvas = jump, right = duck), tracked per `pointerId`. Window blur auto-pauses.
