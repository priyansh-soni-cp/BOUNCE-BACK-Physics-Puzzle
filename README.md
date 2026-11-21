# BOUNCE BACK

**A minimalist 2D physics puzzle game about trajectory deduction, ricochets, and momentum.**

BOUNCE BACK is a physics-driven puzzle game built with **Godot Engine 4.x** for the 2026 hackathon theme **“Bounce Back.”** Each stage blocks the direct route to the goal. Players must work out a sequence of rebounds, use kinetic objects in the environment, and guide the Slime Hopper into the Warp Vortex.

## Features

- **Trajectory-based puzzles:** Plan indirect routes using rebounds rather than relying on a straight shot.
- **Mental mapping:** Use trajectory predictions to reason about collision points and multi-stage ricochets.
- **Distinct physics objects:** Combine spring bumpers, dampener pads, and environmental surfaces.
- **Four handcrafted stages:** Learn the core rebound mechanic, then build toward more complex combinations.
- **Optional collectibles:** Find three Energy Gems per stage for 3-star mastery.
- **Minimalist arcade presentation:** A near-black canvas with neon cyan, crimson, and golden amber accents.
- **Procedural sound:** Sound effects are generated at runtime in GDScript; the project does not rely on external audio files.

## Gameplay

The goal in each stage is to launch the Slime Hopper and guide it into the Warp Vortex. Direct paths are deliberately obstructed, so success depends on predicting how the Hopper will rebound from the environment.

### Physics entities

| Entity | Role | Behaviour |
|---|---|---|
| **Slime Hopper** | Player projectile | Uses custom deterministic bounce physics, gravity compensation (480 px/s²), and squash-and-stretch animation. |
| **Spring Bumper** | Kinetic impulser | Applies a 1.35× velocity boost on collision. |
| **Dampener Pad** | Momentum absorber | Uses a 0.28× rebound coefficient to reduce lateral speed. |
| **Warp Vortex** | Goal | Uses a rotating portal and gravity-based capture field to secure the player on entry. |
| **Energy Gems** | Collectibles | Three optional nodes per stage, placed along optimal rebound routes. |

### Stages

1. **Rebound 101 — Introduction:** Learn to aim away from the goal and use a wall ricochet to get around a vertical divider.
2. **Spring Vault — Bumper Introduction:** Use a floor-mounted spring bumper and an angled ceiling to reach an elevated goal.
3. **Speed Killer — Dampener Mechanics:** Reduce excess momentum with a dampener pad to enter a lower goal chamber.
4. **Apex Arena — Grand Mastery:** Combine multiple rebounds and both bumper interactions in a triple-bounce sequence.

## Technology

- **Engine:** Godot 4.x
- **Rendering:** GL Compatibility renderer
- **Gameplay:** 2D physics and custom bounce behaviour
- **Trajectory preview:** Uses `direct_space_state.intersect_ray` to simulate up to 50 physics steps and estimate predicted surface normals and rebound factors.
- **Audio:** Runtime-generated 16-bit PCM audio encoded into `AudioStreamWAV` buffers using GDScript.
- **Architecture:** `GameManager` and `AudioManager` global singletons; signals are used to decouple systems and coordinate state changes, retries, and stage loading.

## Getting started

### Requirements

- [Godot Engine 4.x](https://godotengine.org/)

### Run the project

1. Clone or download this repository.
2. Open **Godot Project Manager**.
3. Choose **Import** and select the project's `project.godot` file.
4. Open the project and run it using the editor's **Run Project** button.

> **Note:** This report describes the game's design and technical approach. Exact input bindings and any additional setup steps depend on the project configuration; check the project settings or in-game instructions.

## Art and asset credits

The visual direction uses a near-black background (`#08080a`) with neon cyan, rubber crimson, and golden amber accents.

The accompanying game design report states that character, bumper, portal, and platform sprites were curated from free 2D game-jam sprite resources, including Pinterest, OpenGameArt, and itch.io CC0 archives. The source assets are catalogued in `raw_assets_collage.png`.

Please retain the original attribution and licence information for each third-party asset in the repository. Verify the licence and attribution requirements of each asset before redistributing it; do not assume that every asset from a listed site is CC0.

## Project report

The project was documented in **BOUNCE BACK: Game Design & Technical Report — Hackathon 2026 Submission**.

## License

This project is distributed under the **MIT License**. See the [`LICENSE`](LICENSE) file for details.

---

Made for the **“Bounce Back”** hackathon theme.
