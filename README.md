# The Clean Rooms

A browser-based, first-person survival horror game set in an abandoned clean room facility — white halls gone to mold and standing water, half the lights dead, and something in a cleanroom suit still wandering the lower floors. Find the emergency exit on each floor to descend deeper. The further you go, the larger and darker the maze, and the more relentless your pursuer.

Built as a single self-contained HTML file using [Three.js](https://threejs.org/). No build step, no assets to download — every texture, sound, and level is generated procedurally in the browser.

## Play

Play it here: **https://steevd.github.io/clean-rooms/**

Or download `index.html` and open it directly in any modern browser.

## Controls

| Input | Action |
|-------|--------|
| **WASD** / Arrow keys | Move |
| **Mouse** | Look |
| **Shift** | Sprint |
| **Space** | Jump over obstacles |
| **F** | Toggle flashlight |
| **Esc** | Pause menu |

## How it works

- **Procedural levels** — each floor is carved with a recursive-backtracker maze algorithm, guaranteed solvable*, growing larger and tighter as you descend.
- **Navigation** — colored lines on the walls grade from blue (near the entrance) through green to red (the depths, where the exit waits).
- **The pursuer** — from the third floor down, a figure in a cleanroom suit hunts you. It pathfinds through the maze, remembers where it last saw you, and you can hear its breathing grow closer through spatial audio. It's always a little slower than your sprint, so a chase can always be broken.
- **Everything is generated** — textures (mold, water damage, linoleum) are painted with canvas noise, audio is synthesized with the Web Audio API, and the world is rendered with WebGL via Three.js.

*after floor 5 it sometimes becomes unsolvable

## Tech

- Three.js (WebGL rendering)
- Web Audio API (generative ambient sound + spatial entity audio)
- HTML5 Canvas (procedural textures)
- Entirely client-side — runs from a single HTML file, no server

## License

Released under the [MIT License](LICENSE).
