# Algorithm Visualizer

Interactive web app for visualizing pathfinding algorithms and maze/pattern generation on a dynamic grid.

## Overview

This project lets you:

- Visualize weighted and unweighted pathfinding algorithms
- Draw walls and weighted cells on a grid
- Generate random and recursive-division style mazes/patterns
- Add an optional bomb node (an intermediate objective)
- Control animation speed and replay by moving nodes

The app runs on an Express server and serves a browser-based UI.

## Tech Stack

- Node.js
- Express 4
- Vanilla JavaScript (CommonJS modules in browser bundle)
- HTML/CSS + Bootstrap 3

## Implemented Algorithms

Pathfinding:

- Dijkstra's Algorithm
- A\* Search
- Greedy Best-first Search
- Swarm Algorithm (`CLA` mode)
- Convergent Swarm Algorithm (`CLA` + stronger heuristic)
- Bidirectional Swarm Algorithm
- Breadth-first Search (BFS)
- Depth-first Search (DFS)

Maze/Pattern generation:

- Recursive Division
- Recursive Division (vertical skew)
- Recursive Division (horizontal skew)
- Basic Random Maze
- Basic Weight Maze
- Simple Stair Pattern

## Project Structure

- `server.js`: Express server entry point
- `index.html`: main UI shell
- `public/browser/board.js`: board state, events, controls, algorithm orchestration
- `public/browser/pathfindingAlgorithms/`: algorithm implementations
- `public/browser/mazeAlgorithms/`: maze/pattern implementations
- `public/browser/animations/`: visualization animation logic
- `public/styling/`: CSS, icons, images, fonts

Note: There is also a nested `Algorithm Visualizer/` directory that appears to contain a duplicate copy of the project.

## Local Setup

Prerequisites:

- Node.js 16+ (18+ recommended)
- npm

Install dependencies:

```bash
npm install
```

Start server:

```bash
npm start
```

Open in browser:

- `http://localhost:1338`

## How to Use

1. Select an algorithm from **Algorithms**.
2. Draw walls by clicking/dragging on grid.
3. Hold `W` and click/drag to place weighted nodes (cost 15).
4. Optionally click **Add Bomb** to force a two-stage route.
5. Generate a maze/pattern from **Mazes & Patterns**.
6. Click **Visualize!**.
7. Change speed via **Speed** menu or clear board/path/walls from navbar.

## Behavior Notes

- BFS and DFS are treated as unweighted.
- Weighted algorithms use node weight and turning/path costs.
- Moving start/target/bomb after run can trigger instant recomputation.
- Bidirectional Swarm does not support bomb behavior.

## Scripts

From `package.json`:

- `npm start`: runs `nodemon server.js`
- `npm test`: placeholder (currently not implemented)
- `npm run watch`: contains an environment-specific absolute path and likely needs update for this machine

## Known Gaps / Improvements

- No automated test suite yet
- No linter/formatter config
- `watch` script path is hard-coded to another local machine
- Duplicate project directory can cause confusion

## Future Enhancements

- Add unit tests for algorithm correctness and edge cases
- Add CI checks (lint + test)
- Replace hard-coded watch script with portable bundler config
- Add mobile-specific interaction improvements
- Add performance benchmarks and algorithm comparison panel
