# Gloomwood Hardcore Mod

**Gloomwood Hardcore** adds a permanent death mode to Gloomwood. When you die, your save slot is irrevocably deleted – no second chances!

## Features

- **Permanent death** – Upon death, the save folder (`Slot_0` through `Slot_9`) is renamed to `Slot_X_HARDCORE_DEAD`, removing it from the game.
- **Configurable** – Options available in the BepInEx config file (`BepInEx/config/com.wanderan51.gloomwoodhardcore.cfg`):
  - `Enabled` – Turn hardcore mode on/off.
  - `BackupSave` – Keep a `.hardcore_bak` copy of the deleted save.
  - `ShowWarning` – Display a warning banner on the title screen.
  - `DeathDelay` – How long the “YOU DIED” overlay stays visible (0.5–10 seconds).
- **Visual feedback** – A “HARDCORE” badge appears in-game and a bold red banner warns you on the main menu.

## Installation

1. Install **BepInEx** for Gloomwood. (The Thunderstore page for BepInExPack_Gloomwood will guide you.)
2. Place the `HardcoreMod.dll` file into `BepInEx/plugins/`.
3. Launch the game. Your first death will trigger the hardcore deletion.

## Configuration

After running the game once, a config file will appear in `BepInEx/config/`. You can edit it while the game is closed. All options are explained inside.

## How it works

When the mod detects death (by tracking gameplay scenes), it:
- Finds all existing save slot folders (`Slot_0` … `Slot_9`).
- If `BackupSave` is enabled, copies the entire slot folder to `Slot_X_BACKUP`.
- Renames the original slot folder to `Slot_X_HARDCORE_DEAD`.
- Returns you to the title screen and shows a death overlay.

This method is resistant to Steam Cloud because the original path no longer exists, preventing restoration.

## Compatibility

- **Gloomwood** (latest version as of mod release).
- **BepInEx 5.x** (5.4.2100 or newer).

## Known Issues

- If you die in a non‑gameplay scene (e.g., loading screen), the mod may not trigger immediately – but death is typically detected when the next gameplay scene loads.
- Multi‑slot users: all existing slots are deleted at once. The mod does not distinguish which slot you were using; it wipes everything.

## License

This mod is provided under the MIT License. Feel free to modify and share.

---

*For support or suggestions, please open an issue on [GitHub](https://github.com/wanderan51/GloomwoodMods).*