# NOVA Home — Geometry Dash Geode mod

A clean, soft-glass home-screen redesign with a large centre Play tile, smaller Creator and Garage tiles, and optional bottom shortcuts for Settings, Stats and Achievements.

**Targets:** Geode v5.11.2; Geometry Dash 2.2081; Windows 64-bit, Android 32-bit and Android 64-bit.

## How it works
The mod hooks `MenuLayer::init()`, discovers the game's actual buttons by Geode Node IDs, hides only those that were successfully represented by new tiles, and forwards a tile press to the original button via `activate()`. This keeps the original game callbacks and compatible hooks intact. If a required main button is not found, the game keeps its vanilla home screen.

## Settings
Open the mod's Geode settings to change the accent colour, disable the entrance animations, show/hide secondary tiles, and choose whether the title logo gets moved upward. Reenter the home screen after changing settings.

## Building
Use the bundled GitHub Actions workflow, or use a Geode v5 SDK with `geode build -p android64` / `geode build -p android32` / `geode build -p windows`.

The project files are **source**, not a compiled `.geode` binary. The workflow creates the final combined `.geode` artifact on GitHub.

## Compatibility
The design prioritizes 16:9 and other landscape aspect ratios, scales on narrower screens, and leaves extra/unrecognized mod buttons alone. Mods that also fully replace the game's home screen can conflict. Since no local Geode Android/Windows compiler is available in this environment, this is an untested source release; check GitHub Actions logs after building.
