# Spore Extension for NexusMods Vortex

Vortex game extension for **Spore** without the Galactic Adventures expansion
([Nexus page](https://www.nexusmods.com/site/mods/2423)).
For Spore Galactic Adventures and Spore ModAPI (.dll) mods use the
[Galactic Adventures extension](https://www.nexusmods.com/site/mods/2424).

This repository holds the packaged extension (the contents of the archive uploaded to Nexus).
The source of both extensions and the build script live in
[vortex-spore-galactic-adventures](https://github.com/mitay-walle/vortex-spore-galactic-adventures):
`index.js` is shared, `game.js` describes the game.

## Features
- Game detection: Steam (Spore 17390), GOG, EA App / Origin / disc (registry `Electronic Arts\SPORE`)
- "Mod Manager Download" for mods from [nexusmods.com/spore](https://www.nexusmods.com/spore)
- Mods are deployed to the game folder: `.package` files go to `Data` (`Data` / `DataEP1` folders inside an archive are respected)
- `.sporemod` files (loose or inside an archive) are installed from their `ModInfo.xml` like the Spore ModAPI Easy Installer does:
  prerequisites, optional components and component groups (asked in a dialog, remembered for reinstall), compat files
- Files meant for Galactic Adventures are installed to `DataEP1` with a warning, ModAPI (.dll) mods are refused
- 4GB patch: when `SporeBin/SporeApp.exe` is not Large Address Aware, Vortex offers to set the flag
  (the original is kept as `SporeApp.exe.vortex_backup`), skipped for Steam executables (SteamStub DRM)
- Tool: Spore Galactic Adventures, if it is installed in the same folder

## Installation
Click **Vortex** on the Nexus Files tab, or copy the files of this repository into
`%APPDATA%\Vortex\plugins\game-spore` and restart Vortex.
