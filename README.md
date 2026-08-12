# Space Evaders

A 2D physics-based space combat game built in Java. Two players pilot spaceships in a bordered arena, firing missiles and mines while a black hole in the center pulls everything (ships, projectiles, and asteroids) toward it with realistic gravitational acceleration and while asteroids hails from every direction.

## Screenshot

![Space Evaders gameplay screenshot](screenshot.png)

## Features

- **Two-player local combat** — full keyboard controls for both ships simultaneously
- **Realistic gravity** — a black hole spawns mid-game and exerts distance-scaled gravitational pull on every entity; player thrust and gravity combine as independent forces, so projectiles visibly curve as they pass near it
- **Two projectile types** — fast, long-range missiles with spawn immunity, and short-fused mines that detonate after a set time
- **Dynamic hazards** — asteroids spawn from random points along the map edge and are pulled by the black hole just like everything else
- **Custom physics and collision engine** — Polygon-based hitboxes, rotation, and collision detection built from scratch (no game engine/library)

## Controls

| Player 1 | Action | Player 2 | Action |
|---|---|---|---|
| `W` | Thrust forward | `I` | Thrust forward |
| `A` / `D` | Rotate left / right | `J` / `L` | Rotate left / right |
| `S` | Fire missile | `K` | Fire missile |
| `X` | Drop mine | `M` | Drop mine |

## Architecture

- `Game` (abstract) → `SpaceEvaders`: core game loop, rendering, and update cycle
- `Spaceship`: player-controlled entity implementing `KeyListener` for input and `Iterable<Projectile>` (via a custom anonymous `Iterator`) to manage active projectiles
- `Missile` / `Mine`: inner classes of `Spaceship` sharing a common `Projectile` interface
- `BlackHole`: applies distance-scaled gravitational acceleration to all entities each frame
- `Asteroid`: randomly-spawned hazard with its own trajectory and collision handling
- `Polygon` / `Point`: shared geometry classes used for hitboxes, rotation, and rendering across all entities

## Running the game

**Requirements:** Java JDK 8+

```bash
git clone https://github.com/Hgupta1912/space-evaders.git
cd space-evaders
```
Then run SpaceEvaders.java
