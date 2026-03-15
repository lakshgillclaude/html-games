# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains standalone HTML5 games. Each game is a single self-contained HTML file with embedded CSS and JavaScript - no build tools, bundlers, or external dependencies.

## Running Games

Open any `.html` file directly in a web browser. No server or build step required.

## Architecture Pattern

All games follow the same single-file architecture:

```
<!DOCTYPE html>
<html>
<head>
    <style>/* All CSS here */</style>
</head>
<body>
    <!-- Minimal HTML structure -->
    <script>/* All JavaScript here */</script>
</body>
</html>
```

### Game-Specific Patterns

**Simple DOM Games (tictactoe.html)**
- Uses DOM elements for game board
- CSS Grid for layout
- Event listeners on DOM elements
- State stored in simple variables/arrays

**Canvas Games (shooter.html)**
- HTML5 Canvas for rendering (800x600)
- `requestAnimationFrame` game loop with delta time
- State machine for game states (MENU, PLAYING, LEVEL_TRANSITION, GAME_OVER)
- ES6 classes for entities (Player, Enemy, Bullet, PowerUp, Particle)
- Keyboard state tracking via `keys` object for smooth input
- Web Audio API oscillator-based sound effects
- AABB collision detection

## Conventions

- No external dependencies or CDN imports
- Retro/simple geometric rendering style
- Dark gradient backgrounds
- Monospace fonts (Courier New) for canvas games
- All game constants defined at script top
- Entity classes handle their own update() and draw() methods
