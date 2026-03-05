# FFT Ivalice Editor v2.5.0

A standalone GUI editor for **FINAL FANTASY TACTICS: The Ivalice Chronicles** (2025 Steam remaster, Enhanced version).

## Features

### Job Editor
- Edit job stats: HP/MP/Speed/PA/MA growth & multipliers, Move/Jump/C-Evasion
- Set innate abilities (4 slots), equipment flags, elemental affinities
- Status immunities, starting statuses, innate statuses
- Monster portrait/palette/graphic settings
- Named dropdowns for all abilities and skillsets

### Skillset Editor
- Edit skillsets: 16 action ability slots + 6 RSM (Reaction/Support/Movement) slots
- All ability slots use searchable dropdowns with full ability names
- Extended skillset support (176-226) for monster/WOTL content with warnings

### Difficulty Editor
- Edit the 3 difficulty levels: Squire (Easy), Knight (Normal), Tactician (Hard)
- 4 percentage-based modifiers per level: Enemy HP, Enemy Damage, Player HP, Player Damage
- Quick presets: Vanilla Defaults, All Equal (100%), Extreme Hard
- Intuitive tooltips explaining each modifier

### Raw Data Tabs (NXD/SQLite)
- **Abilities**: Names, descriptions, JP costs, icons
- **Ability Parameters**: Range, area, element, formula, X/Y, CT, MP overrides
- **Items**: Names, descriptions, categories
- **Job Unlock Requirements**: Required jobs and levels
- **Encounters**: Unit jobs, equipment, abilities per encounter

### Save Editor (Experimental)
- Load and edit FFT save files (enhanced.png)
- Change character jobs across all 50 save slots
- Auto-detects save file location
- Creates backups before saving

> **Warning**: Save editing is experimental. The save format is not fully documented.
> Always keep backups. Changes may cause issues with existing saves.

## Requirements
- Windows 10/11
- .NET 9.0 Runtime (required by FF16Tools)
- FINAL FANTASY TACTICS: The Ivalice Chronicles (Steam)

## Usage
1. Run `FFT Editor.exe`
2. Set your game path if not auto-detected
3. Click **Extract & Load** to load game data
4. Edit using the tabs
5. Click **Save & Pack** to apply changes

## How It Works
- **NXD data** (abilities, items, encounters) → packed into `modded.pac` overlay that the game auto-loads
- **EXE data** (job stats, skillsets, innate abilities) → binary patched directly into `FFT_enhanced.exe` (backup created as `.bak`)
- **Difficulty data** → edited in NXD DifficultyLevel table → packed into `modded.pac`
- Both types of changes persist permanently across all saves and new games

## Credits & Acknowledgments

### Tools
- **[FF16Tools.CLI v1.12.0](https://github.com/Nenkai/FF16Tools)** by Nenkai — NXD/PAC extraction, SQLite conversion, save file unpacking/packing
- **[FFTPatcher](https://github.com/Glain/FFTPatcher)** by Glain — WotL ability default data (Abilities.bin) used for the Ability Parameters tab reference values
- **[FFHacktics](https://ffhacktics.com/)** community — Formula reference data, ability/job research, and modding documentation

### Libraries
- **[Python](https://www.python.org/)** 3.14 — Runtime
- **[PySide6](https://doc.qt.io/qtforpython-6/)** (Qt for Python) — GUI framework
- **[Pillow (PIL)](https://pillow.readthedocs.io/)** — Portrait image processing (DDS → PNG conversion)
- **[PyInstaller](https://pyinstaller.org/)** — Executable packaging

### Built With
- **[Claude Code](https://claude.ai/claude-code)** by Anthropic — AI-assisted development

### Special Thanks
- **NinGeoWeazeleff** — Testing and feedback
