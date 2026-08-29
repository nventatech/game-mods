# Give Me Everything - Dying Light

In-game cheat menu for Dying Light 1, plus the developer menu Techland left hidden in the game.

## Install

1. Copy `winmm.dll` into the game folder, next to `DyingLightGame.exe`.
2. Set the game to **Borderless** or **Windowed** (the overlay does not draw in exclusive fullscreen).
3. Press **Insert** in game, or click both analog sticks (L3+R3) on a gamepad.

To uninstall, delete `winmm.dll`. Nothing else is touched.

On Linux/Steam Deck add this to the game's launch options:

```
WINEDLLOVERRIDES="winmm=n,b" %command%
```

## What it does

- 78 toggles across Player, Combat, Enemies, Items, Vehicle and World.
- Unlocks the game's own developer screens (give items, loot, teleport, progress, variables) from the pause menu.
- Keyboard and gamepad, searchable list, settings saved between sessions.
- Follows the game language. Portuguese is built in.

Options that need The Following, Bozak Horde or Hellraid only show up if you own them.

## Notes

- Single player. In co-op the cheats turn themselves off; you can override that in Settings, at your own risk. Co-op with cheats needs **VAC Secure Game** off in Options > Online.
- Other mods are left alone: the pause menu entries are built in memory from whatever the game already loaded, so `Data3.pak` is never modified.
- Problems are logged to `gme_log.txt` next to the DLL.

## Translating

Copy `lang/gme_lang_pt-br.txt` to `gme_lang_<code>.txt`, put it next to the DLL and translate the right side of each line. The mod picks it up automatically when the game runs in that language.

## Build

```
cd src
cmake -B build -DCMAKE_TOOLCHAIN_FILE=toolchain-mingw.cmake -DCMAKE_BUILD_TYPE=Release
cmake --build build -j
```

Output: `src/build/winmm.dll`.

- `tools/gen_patches.py` turns `patterns.json` + `patterns_cave.json` into `src/patches_data.cpp`.
- `tools/gen_lang.py` embeds the Portuguese file into the binary.
- `tools/package.sh <version>` builds the release zip.
