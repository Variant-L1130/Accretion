# Accretion

**A physics-based survival game about growing from a tiny glowing protostar into a quasar-powered black hole.**

Eat what's smaller than you. Run from what's bigger. Survive as long as you can.

**[▶ Play it here](https://variant-l1130.github.io/Accretion/)** — runs in any modern browser on desktop and Android, nothing to install.

---

## How to play

Your mass is your power. Anything much smaller than you is pulled in automatically, like a magnet, and added to your mass. Anything bigger can swallow you. Your score is how long you survive.

- **Smaller objects** (gas, dust, planets, small stars and black holes) fall toward you and are absorbed.
- **Similar-sized stars and black holes** can be merged with if you are the heavier one. You grow a lot and get a temporary growth boost. If they are heavier, they swallow you.
- **Bigger objects** (giant asteroids, large stars, bigger black holes) are dangerous. Red rings, edge arrows and the radar show where they are.
- **Planets** orbit stars. Pull them out of orbit and eat them to grow.
- **THE APEX**, a hunting rival black hole, appears once you become a black hole.

### Controls

| Action | Keyboard | Touch (Android) |
|---|---|---|
| Steer | WASD / arrow keys, or drag | On-screen joystick |
| Dash (also breaks free of gravity for a moment) | Space | DASH |
| Stronger gravitational pull | Shift | PULL |
| Gravitational wave (pushes nearby objects away) | E | WAVE |
| Relativistic jet (quasar stage only) | F | JET |
| Settings | Esc or the ⚙ button | ⚙ button |
| Fullscreen | ⛶ button | ⛶ button |

Settings include sensitivity, sound volume, screen shake, zoom and a visual-effects toggle. They are saved in your browser. On a phone, play in landscape.

---

## Stages

Mass is shown in solar masses (M☉, the mass of the Sun). You start at 0.01 M☉. All thresholds are game values, not real astrophysics.

| Stage | Reached at | Notes |
|---|---|---|
| Protostar | start | A small glowing ball that collects gas and dust |
| Young star | 1 M☉ | "Stellar ignition" |
| Main-sequence star | 10 M☉ | Survival phase |
| Massive star | 40 M☉ | Starts a 22-second core-fuel timer |
| Black hole | when the timer ends | "Stellar collapse"; the Apex appears |
| Quasar | 400 M☉ | Bright disk, screen glow, jets unlocked |
| Supermassive quasar | 4,000 M☉ | Late game |
| Cosmic Giant | 40,000 M☉ | The camera zooms out further; keep playing |

As a black hole, swallowed matter first goes into the accretion disk and joins your mass at a limited rate, a simplified version of the Eddington limit.

The camera zooms out automatically as you grow, and difficulty rises slowly with both time and your size.

---

## Features

- Magnet-style auto-absorption and mass-based gravity
- Procedurally spawned stars, planets with orbits, asteroids, gas clouds and rival black holes
- Merging with similar-sized stars and black holes
- Stellar ignition, a stellar-collapse sequence, black-hole and quasar visuals
- Tidal stripping of smaller black holes
- A hunting rival (THE APEX) that follows the same simplified physics
- Radar minimap showing threats and food
- Procedural sound (Web Audio), with no audio files
- Fullscreen, on-screen joystick and buttons for touch
- Local leaderboard (top runs on your device)
- Settings panel

---

## Tech

- HTML5, CSS3 and plain JavaScript in a **single file** (`index.html`), with no frameworks or libraries
- Canvas 2D rendering with a custom `requestAnimationFrame` game loop
- Custom physics: softened gravity, orbital velocity, inertia, collisions and merging
- Web Audio API for generated sound effects and a low drone
- Pointer Events for mouse and touch input, the Fullscreen API, `localStorage` for settings and the leaderboard
- Hosted on GitHub Pages

### Physics approximations

The game is physics-inspired, not a simulation. Gravity strength scales with object radius cubed as a stand-in for G·M, with softening to avoid singularities. Heavier bodies accelerate less toward the player. Orbits use the circular-orbit speed v = √(GM/r). The Eddington-style limit caps how fast disk matter joins the black hole. Mass thresholds are tuned for gameplay.

---

## Run it locally

No build step. Download `index.html` and open it in a browser.

To serve it locally instead:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

On GitHub: Settings → Pages → Deploy from a branch → `main` / `(root)`. The file must be named `index.html` and the repository must be public on a free account.

---

## Known limitations

- The leaderboard is stored per browser and device. It is not shared between players.
- Performance on very low-end phones may vary. Turn off Visual effects in Settings if it stutters.
- Fullscreen is not available in every mobile browser.

## Credits

Designed by **Atharv**. The code was written with help from Claude, an AI assistant made by Anthropic, based on my game design and requirements. All names, visuals and code are original.

## License

MIT. Add a `LICENSE` file if you want this to be official.
