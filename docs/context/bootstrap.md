# InkyPi — Degraded Mode Context

Legacy fallback context. Current agent entrypoint: `AGENTS.md`, which inherits the workspace contract from `~/workspace/AGENTS.md`.

## Owner

Steve Coveney. Public open-source project.

## Purpose

E-Ink display app for Raspberry Pi with a web interface. Displays clock, weather, AI-generated images/text, newspaper front pages, and custom images. Plugin-based architecture.

## Key Entry Points

- `src/inkypi.py` — main entry point
- `src/display_manager.py` — display refresh and plugin execution
- `src/plugins/` — all plugins; inherit from `base_plugin`
- `src/blueprints/` — Flask routes
- `install/install.sh` — Raspberry Pi OS installer (requires sudo)

## Plugin Development

Plugins inherit from `base_plugin`. See `docs/building_plugins.md`.

## Requirements

- Raspberry Pi (4 / 3 / Zero 2W) + Inky Impression E-Ink display (Pimoroni)
- OpenAI API key for `ai_image` and `ai_text` plugins
- SPI and I2C interfaces enabled (handled by install script)
