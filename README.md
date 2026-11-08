<div align="center">

# vini's MAC10

The Ingram MAC-10 in .45 ACP for SPT 4.1.6: full auto only at 1090 RPM, a folding wire stock, its own suppressor, a long barrel, railed shrouds and barrel extensions.

![Version](https://img.shields.io/badge/version-1.0.0-orange?style=flat)
![SPT](https://img.shields.io/badge/SPT-4.1.6-blue?style=flat)
![WTT-CommonLib](https://img.shields.io/badge/WTT--CommonLib-3.0.6-purple?style=flat)
![.NET](https://img.shields.io/badge/.NET-10-512BD4?style=flat&logo=dotnet)
![License](https://img.shields.io/badge/license-MIT-green?style=flat)

[Features](#features) · [Install](#install) · [The Gun](#the-gun) · [Attachments](#attachments) · [Build](#build-from-source)

</div>

---

## Features

- **Ingram MAC-10 .45 ACP**: full auto only at 1090 RPM, with a 30-round magazine.
- **Attachments**: a two-stage suppressor, a long barrel, four railed shrouds and three barrel extensions. See [Attachments](#attachments).
- **Rails**: the shrouds take sights, lights and lasers on top. The Tall Double and the Large also take foregrips underneath, limited to the ones that fit the shroud.
- Everything is sold by Peacekeeper.

---

## Install

Install [WTT-CommonLib](https://github.com/WelcomeToThursday/WTT-CommonLib) **3.0.6** or newer (3.0.x) first. Then download `mac10.zip` from [Releases](https://github.com/viniHNS/mac-10/releases) and extract it into your SPT game folder:

```
<game folder>/
└── SPT_Runtime/user/mods/mac10/
    ├── mac10.dll
    ├── bundles.json
    ├── bundles/            models, textures and animations
    └── db/                 items, preset, trader offers and locales
```

Server only, no client plugin needed.

> The new items stay in your profile. Removing the mod after buying them breaks the profile.

---

## The Gun

| | |
|---|---|
| Caliber | .45 ACP |
| Fire mode | Full auto |
| Rate of fire | 1090 RPM |
| Magazine | 30 rounds |
| Weight | 2.4 kg |
| Ergonomics | 58 |
| Recoil (vertical / back) | 95 / 380 |
| Sold by | Peacekeeper LL1: barter for 2 Damaged hard drives + 1 CPU fan (5 per restock)<br>Peacekeeper LL2: $300 (limit 2) |

---

## Attachments

All attachments are sold by Peacekeeper.

| Item | Mounts on | Effect | Peacekeeper |
|---|---|---|---|
| 30-round magazine | Gun | | LL1, 1 Bottle of Tarkovskaya vodka (10 per restock)<br>LL2, $13 |
| Telescoping wire stock | Gun | Recoil −22%, ergonomics +3 | LL2, $20 |
| Two-stage sound suppressor | Barrel muzzle | Loudness −27, recoil −8%, ergonomics −14, velocity +0.7% | LL3, $360 |
| 146mm barrel with extension | Barrel slot | Velocity +3%, recoil −4%, ergonomics −4; nothing mounts on its muzzle | LL2, $95 |
| Railed shroud (Single) | Barrel muzzle | Top rail | LL2, $30 |
| Railed shroud (Tall) | Barrel muzzle | Tall top rail | LL2, $30 |
| Railed shroud (Tall Double) | Barrel muzzle | Top and bottom rails | LL2, $38 |
| Railed shroud (Large) | Barrel muzzle | Top and bottom rails | LL2, $45 |
| 3" barrel extension | Barrel muzzle | Velocity +0.5%, recoil −1% | LL2, $25 |
| 6" barrel extension | Barrel muzzle | Velocity +1.0%, recoil −2% | LL2, $32 |
| 9" barrel extension | Barrel muzzle | Velocity +1.5%, recoil −3% | LL2, $38 |

The shrouds and the barrel extensions are not threaded: nothing mounts on their muzzle.

---

## Build from Source

**Requirements:** .NET 10 SDK.

```sh
dotnet build mac10.sln -c Release
```

The build creates `mac10.zip` in the project folder.

> The `.csproj` copies the build output into `D:\Jogos\SPT4.1\SPT_Runtime\user\mods` for testing when that folder exists. Change `SptModsDir` to your own SPT folder. Close the SPT server before building, or the copy fails because the DLL is in use.

### Project Structure

```
mac-10/
├── mac10.sln
├── mac10.csproj
├── Mod.cs                          mod metadata and loading (WTT-CommonLib)
├── bundles.json                    bundle manifest
├── bundles/                        models, textures and animations
└── db/
    ├── CustomItems/mac10.json      items, slots and locales (EN, PO, RU)
    └── weaponPresets/
        ├── GlobalPresets/          default preset
        └── Assorts/                Peacekeeper offers
```

---

## Credits

- MAC-10, magazine, suppressor, barrel extensions and railed shrouds: models and textures from Hot Dogs, Horseshoes & Hand Grenades (RUST LTD), retextured for the game's shaders.

---

## Resources

| Resource | URL |
|---|---|
| WTT-CommonLib | https://github.com/WelcomeToThursday/WTT-CommonLib |
| SPT Server C# | https://github.com/SP-Tushonka/server-csharp |
| Server Mod Examples | https://github.com/SP-Tushonka/server-mod-examples |
| SPT Wiki — Modding Resources | https://wiki.sp-tushonka.com/en/modding/Modding_Resources |
| SPT Scaffold | https://github.com/viniHNS/spt-scaffold |
