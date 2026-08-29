# UltrawideUI - Dying Light

HUD at the screen edges on 21:9 monitors.

## Install

1. Go to the game folder, then `DW/`.
2. Open `Data3.pak` with 7-Zip or WinRAR (it is a zip file, do not extract it).
3. Drag the mod's `data` folder into it, replacing files if asked.
4. Close the archive and play.

Works alongside other Data3.pak mods: you are only adding `data/menu/hud/`, nothing else in the pak is touched. Back up `Data3.pak` first if you want to undo it later.

## Notes

- Layout tuned for 3440x1440 and 2560x1080. 32:9 not supported yet.
- Cutscenes keep their black bars. That needs an engine patch, not a pak.

## Build

`tools/gen_pak.py <Data0.pak> <out.pak> [aspect]` rewrites the HUD positions from the vanilla file. `tools/package.sh <version>` builds the release zip.
