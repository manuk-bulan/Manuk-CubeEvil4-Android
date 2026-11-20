# ManukCubeEvil4 — CubeEvil4 Manuk Bulan Edition

![Beta](https://img.shields.io/badge/Status-Beta-E67E22)
![Android 7.0+](https://img.shields.io/badge/Android-7.0%2B-3DDC84?logo=android&logoColor=white)
![ARM 32/64-bit](https://img.shields.io/badge/ARM-32%2F64--bit-0091BD?logo=arm&logoColor=white)
![OpenGL ES 3.0+](https://img.shields.io/badge/OpenGL%20ES-3.0%2B-5586A4?logo=opengl&logoColor=white)
![Vulkan](https://img.shields.io/badge/Vulkan-experimental-AC162C?logo=vulkan&logoColor=white)
![Input](https://img.shields.io/badge/Input-Touch%2FGamepad%2FKeyb%2BMouse-9A1B1C)

[![Telegram](https://img.shields.io/badge/Telegram-Community-26A5E4?logo=telegram&logoColor=white)](https://t.me/re4andriyanblaze)
[![Trakteer](https://img.shields.io/badge/Support-Trakteer-be1e2d)](https://trakteer.id/andriyanblaze/)

**[WHAT'S NEW](#whats-new-in-the-manuk-bulan-edition) | [REQUIREMENTS](#requirements) | [HOW TO USE](#how-to-use) | [COMMUNITY](#community) | [RELEASES](https://github.com/manuk-bulan/CubeEvil4-Android/releases)**

**ManukCubeEvil4** is a modded build of **[CubeEvil4](https://github.com/Andiweli/CubeEvil4-Android)** by "Andiweli" the native Android port of the Resident Evil 4 GameCube prototype
(`G4BE08` Nov 2004 debug build), with controller support and OpenGL ES 3 / Vulkan (experimental).
It adds features for players who like to tinker and mod.

It plays the **European** (`G4BP08`), **US** (`G4BE08`) and **Japanese** (`G4BJ08`) retail releases
and contains no game data: you need your own images of both discs of your own copy.

> [!NOTE]
> This repository hosts the **releases** of the Manuk Bulan Edition only. The source code of the base
> project lives at [Andiweli/CubeEvil4-Android](https://github.com/Andiweli/CubeEvil4-Android).
> ManukCubeEvil4 installs **next to** the original CubeEvil4 (app id `com.manukbulan.cubeevil4`); it
> does not replace it.

> [!TIP]
> **Play the Resident Evil 4 remake.** Capcom's *Resident Evil 4* (2023) rebuilds the original for
> today's consoles and PCs. If you enjoy this port, please consider buying the remake and supporting
> the people who made Resident Evil: [residentevil.com/re4](https://www.residentevil.com/re4/)


## About this project

ManukCubeEvil4 is a non-commercial fan project made out of love for Resident Evil 4. It is free,
nothing in it is sold, and no feature is locked behind a payment.

All credit for the game, its story, characters, art, music and design belongs to Capcom and to the
original development team. All credit for the Android port belongs to
[Andiweli](https://github.com/Andiweli/CubeEvil4-Android). If you do not own the game, please buy
it: the remake or one of the official re-releases.


## What's new in the Manuk Bulan Edition

**Game folder outside the app**
- Game data lives in `/storage/emulated/0/ManukCubeEvil4/`, easy to reach and edit.
- Uninstalling the app does not delete it. An older `CubeEvil4` folder is moved over once, saves stay safe.

**No disc import needed**
- `disc1` and `disc2` take `.iso` / `.gcm` / `.nkit.iso` (read directly), a Dolphin extract (`sys` + `files`),
  or `.rvz` (converted to ISO once, inside the app).
- **SCAN FOLDER** finds your discs on the device by itself.

**Mod loader**
- Put modded asset files into `ManukCubeEvil4/mods/` (any subfolder, e.g. `mods/krauser boss/pl0a.drs`).
- A file with the same name replaces the disc's; everything else comes from the disc. The discs are never changed:
  delete the mod file to go back to the original.

**Cheats**
- **Add item:** every GameCube item, grouped by type (handguns, magnums, shotguns, rifles, machine guns, special
  weapons, grenades, ammo, accessories, recovery, treasures, cases M/L/XL). Items the GameCube version does not
  have (such as the P.R.L. 412) are left out, so they cannot crash the game.
- **Stack limit:** Normal, 69, 100, 500, 800, 999 or Custom (up to 999) per slot for ammo, grenades, sprays,
  herbs, eggs and fish. Weapons stay one per slot.
- **HUD colour:** normal, preset colours, your own `#RRGGBB`, or RGB fading with slow / medium / fast speed.
  Yellow and red still warn of low health.
- **HUD & minimap position:** drag the life gauge and the minimap anywhere, live. Inventory, map and merchant
  keep the original layout.
- **POV** *(experimental)*: field of view 50–400 % on a live slider (100 = normal). Scope, binoculars,
  cutscenes and menus stay normal.
- **Krauser boss → Run boss** *(experimental)*: every character runs with Krauser's boss run and stands in his
  bow pose, with any weapon.

**Crash log**
- If the app force-closes, `crash_log.txt` appears in the `ManukCubeEvil4` folder. Send it with your bug report.


## What the app does (from CubeEvil4)

- The whole game code (all 114 REL modules) runs natively as ARM32 and ARM64 in one APK; only the GameCube
  platform layer is replaced (graphics, video timing, OS, disc, controller, sound, memory card, ARAM, movies).
- Graphics: the game's GX commands translated to OpenGL ES 3, at 1080p and above, with optional anti-aliasing,
  anisotropic filtering and depth of field; Vulkan is experimental.
- Sound: the original SDK sound libraries with an emulated DSP; movies through the original CRI middleware.
- Memory card with `.gci` import and export (Dolphin, GameCube).
- GameCube-style controller layout with vibration, Alternate Controls, touch controls, gyro aiming, knife by
  swipe, latching L / R / B and Controller Configuration.
- Optional HD texture packs in the Dolphin format that you obtained yourself (converted with the CubeEvil4
  Texture Packer from the [original releases](https://github.com/Andiweli/CubeEvil4-Android/releases)).
  No textures are included.


## Requirements

| Class | SoC | GPU | Suitability |
|:-----:|-----|-----|-------------|
| **A** | Snapdragon 8 Elite (Gen 1 – Gen 6), Dimensity 9500 / 9600 Pro | Adreno 830–845, Mali-G1 Ultra | high resolution, no limits |
| **B** | Snapdragon 8 Gen 2 / Gen 3, Dimensity 9300 / 9400 | Adreno 740 / 750, Immortalis-G720 / G925 | 60 fps at high resolution |
| **C** | Snapdragon 8 Gen 1 / 8+ Gen 1 / 8s Gen 3 / 888 / 870 / 865 | Adreno 650–735 | smooth, 30–60 fps |
| **D** | Snapdragon 7 series / 695 / 778G, Dimensity 900 / 920 / 8xxx, Exynos 1280 / 1380 | Adreno 619–642, Mali-G68 / G610 | 30 fps at reduced resolution |
| **E** | Dimensity 700–810, Helio G80–G99, Exynos 850, Unisoc T6xx, Snapdragon 4 series | Mali-G57 / G52, Adreno 610 and below | heavily reduced, often stutters; not recommended |

| | Minimum | Recommended |
|---|---|---|
| Android | 7.0 | – |
| Processor | ARM, 32- or 64-bit | 64-bit |
| Graphics | OpenGL ES 3.0 | – |
| RAM | – | 4 GB or more |
| Input | touch screen or a game controller | a game controller |
| Game data | your own images of **both** discs of the European, US or Japanese retail release | – |


## How to use

1. Download the APK from **[Releases](https://github.com/manuk-bulan/Manuk-CubeEvil4-Android/releases)**, install it
   and open **ManukCubeEvil4**.
2. Allow **All files access** when asked.
3. Put your discs into `ManukCubeEvil4/disc1` and `ManukCubeEvil4/disc2` (ISO, GCM, NKit ISO, RVZ or a Dolphin
   extract), or tap **SCAN FOLDER**. Both discs must be of the same release.
4. Tap **Start game**.

**SELECT** (with touch controls: **MENU**) opens the app menu: graphics, sound, controls, performance, cheats &
mods, memory card and the error report. **B** returns to the game.

| Controller | GameCube | In the game |
|---|---|---|
| A, B, X, Y | A, B, X, Y | by their labels |
| Left stick | Control stick | move |
| Right stick | C stick | aim (Alternate Controls) |
| R2 / L2 | R / L | ready weapon / knife |
| R1 | Z | map |
| START / SELECT | START / – | pause / app menu |


## Community

- **Telegram (Manuk Bulan Edition):** [t.me/re4andriyanblaze](https://t.me/re4andriyanblaze)
- **Discord (original CubeEvil4, The Lair):** [discord.gg/AB3WVBqD5G](https://discord.gg/AB3WVBqD5G)

Found a bug? Report it on Telegram with a screenshot, a short video or the log (`crash_log.txt`, or the app
menu → Error report).


## Support

If ManukCubeEvil4 helps you and you want to support further development:

[![Support on Trakteer](https://img.shields.io/badge/Support%20on-Trakteer-be1e2d?style=for-the-badge)](https://trakteer.id/andriyanblaze/)


## Credits

- **[Andiweli](https://github.com/Andiweli/CubeEvil4-Android)**: CubeEvil4, the Android port this edition is based on.
- **[adonis-singh](https://github.com/adonis-singh/re4)**: the decompilation of the debug build that the port is built on.
- **Capcom** and the original development team: Resident Evil 4.
- **Manuk Bulan**: the Manuk Bulan Edition features.


## Legal

- **Unofficial fan project.** ManukCubeEvil4 is a non-commercial fan project. It is not affiliated with,
  endorsed by, sponsored by or approved by Capcom Co., Ltd., Nintendo Co., Ltd. or CRI Middleware Co., Ltd.
- **Trademarks.** Resident Evil, Biohazard and all related names, characters and logos are trademarks or
  registered trademarks of Capcom Co., Ltd. GameCube and Nintendo are trademarks of Nintendo. CRI, ADX and
  Sofdec are trademarks of CRI Middleware. Android is a trademark of Google LLC. They are named here only to
  say which game and platform the port is about.
- **Copyright.** Resident Evil 4 © CAPCOM CO., LTD. 2005. The game, its code, data, story, characters, art,
  music and sound are the property of Capcom; the GameCube SDK of Nintendo; the CRI middleware of CRI Middleware.
- **No game data.** No game data, disc images, BIOS or other copyrighted assets are included or distributed.
  You need your own legally obtained copy of the game.
- **No texture packs.** No replacement textures are included or linked.
- **No warranty.** The app is provided "as is", without any warranty. Use it at your own risk.
