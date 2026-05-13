# Project: InkyPi

## Bootstrap
Read `~/workspace/AGENTS.md` for the team contract (Larry orchestration, identity, governance, session protocols).

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
- Team Knowledge paths from the inherited myPKA contract resolve to `~/workspace/Team Knowledge/...`, not this subproject root.
- Deputy dispatch is serial-only in subproject sessions (voice-switching). Launch Claude Code in `~/workspace/` when vault-scoped host shims are needed for parallel deputy dispatch.

- Follow existing project structure — this is a public open-source repo. Don't restructure.
- Plugins inherit from `base_plugin`. See `docs/building_plugins.md` for the plugin API.
- Installation requires sudo on Raspberry Pi OS (SPI/I2C interfaces, systemd service).
- OpenAI API key required for AI plugins (`ai_image`, `ai_text`).

## What NOT to do

- Do not commit API keys or credentials.
- Do not restructure directories — follow existing conventions.
- Do not break the plugin registry interface when adding plugins.
