# InkyPi

## Identity & Context
Read ~/workspace/knowledge/maps/me.md
Read ~/workspace/knowledge/maps/workspace-map.md

If shared knowledge is unavailable, read docs/context/bootstrap.md and continue in degraded mode.

## This Project

Open-source E-Ink display app for Raspberry Pi with a web interface. Python/Flask backend, plugin architecture for display content (clock, weather, AI image/text, newspaper, image upload).

- **`src/inkypi.py`** — entry point
- **`src/display_manager.py`** — manages display refresh and plugin execution
- **`src/plugins/`** — plugin registry + individual plugins (ai_image, ai_text, clock, weather, newspaper, image_upload, screenshot)
- **`src/blueprints/`** — Flask route blueprints
- **`src/config.py`** — configuration loader
- **`install/`** — installation scripts for Raspberry Pi OS
- **`scripts/`** — utility scripts
- **`docs/`** — plugin development docs, community builds, installation guide

## Conventions

- Follow existing project structure — this is a public open-source repo. Don't restructure.
- Plugins inherit from `base_plugin`. See `docs/building_plugins.md` for the plugin API.
- Installation requires sudo on Raspberry Pi OS (SPI/I2C interfaces, systemd service).
- OpenAI API key required for AI plugins (`ai_image`, `ai_text`).

## What NOT to do

- Do not commit API keys or credentials.
- Do not restructure directories — follow existing conventions.
- Do not break the plugin registry interface when adding plugins.
