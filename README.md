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

## Goal and progression

**The goal:** evolve through all 22 stages to become a **Cosmic Giant**, and beat your best survival time.

Evolution depends on **mass only**. There are no timers or tasks. Each stage needs a larger mass target, spaced so a player spends roughly 1.5 to 2 minutes in each stage.

Eating objects quickly builds a **combo** that gives up to 60% bonus mass. The HUD shows your best survival time, and a banner appears when you beat it.

### Who can eat whom

Every object roaming space is one of the stages below.
- **A lower stage than yours** is food. You swallow it. Smaller bodies first circle you, then spiral in.
- **A higher stage than yours** is a threat, marked with a red ring and a name label. Touching it ends the run, and the death screen says what killed you (for example "Killed by: Neutron Star" or "A giant asteroid").
- **The same stage as yours** merges with you. You first orbit each other, then collapse into one larger body, and a shockwave hurls nearby matter away.
- **Giant asteroids** are early threats. Larger bodies carry planets and debris that orbit them.
- **Bigger black holes engulf smaller ones**, including rivals.
- **Cosmic Giants:** once you are one, larger Cosmic Giants appear to end your run.
- **Supernovae and hypernovae** appear as rare blasts that push things away.

---

## Stages

Mass is shown in solar masses (M☉, the mass of the Sun). You start at 0.01 M☉. All thresholds and powers are game values, not real astrophysics.

| # | Stage | Reached at | Power |
|---|---|---|---|
| 1 | Stellar Nebula | start | Wide diffuse pull, slow steering |
| 2 | Protostar | 0.03 M☉ | A small hot core |
| 3 | Pre-Main-Sequence Star | 0.08 M☉ | Stronger pull as you contract |
| 4 | Brown Dwarf | 0.2 M☉ | Compact and dim |
| 5 | Red Dwarf | 0.55 M☉ | Quick dashes |
| 6 | Yellow Dwarf | 1.5 M☉ | Absorbs matter more efficiently |
| 7 | Blue Main-Sequence Star | 4 M☉ | Stellar wind pushes big hazards away |
| 8 | Red Giant | 11 M☉ | Large reach and pull, sluggish |
| 9 | Red Supergiant | 30 M☉ | Enormous reach, slow and easy to hit |
| 10 | Blue Supergiant | 80 M☉ | Fast, with a strong stellar wind |
| 11 | Luminous Blue Variable | 220 M☉ | Erupting and unstable |
| 12 | Planetary Nebula | 600 M☉ | Sheds its shell for about 6 s; you are protected |
| 13 | Supernova | after the nebula | About 10 s; repeated shockwaves hurl nearby matter away; protected |
| 14 | Hypernova | after the supernova | About 12 s; stronger shockwaves; protected |
| 15 | White Dwarf | after the hypernova | Tiny, dense, stronger gravity |
| 16 | Black Dwarf (theoretical) | 1,600 M☉ | Stealth: rivals struggle to track you |
| 17 | Neutron Star | 4,400 M☉ | Pulsar beams vaporize small objects |
| 18 | Stellar Black Hole | 12,000 M☉ | Event horizon, accretion disk, the Apex appears |
| 19 | Supermassive Black Hole | 33,000 M☉ | Larger disk and reach |
| 20 | Quasar | 90,000 M☉ | Bright disk and jets (F / JET) |
| 21 | Supermassive Quasar | 240,000 M☉ | Rival giants roam |
| 22 | Cosmic Giant | 650,000 M☉ | The camera zooms out further; keep playing |

Stages only go up. The death sequence (planetary nebula, supernova, hypernova) is a game simplification: real stars follow only one of these paths depending on their mass.

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

Designed by **Atharv**.
