# VansonMod

<p align="center">
  <img src="https://repository-images.githubusercontent.com/1109090336/135167c3-e943-48a9-aa0d-67b3c21e844d" alt="VansonMod Social Preview" width="100%"/>
</p>

**iOS memory editor, iOS pointer analysis, RVA patcher, and process manager for TrollStore (jailbreak optional). Supports hex editing, value scanning, and backup/restore.**

**English** | [简体中文](./docs/README_CN.md) | [繁體中文](./docs/README_TW.md) | [العربية](./docs/README_AR.md) | [Deutsch](./docs/README_DE.md) | [Español](./docs/README_ES.md) | [Français](./docs/README_FR.md) | [日本語](./docs/README_JA.md) | [한국어](./docs/README_KO.md) | [Português](./docs/README_PT.md) | [Русский](./docs/README_RU.md) | [ไทย](./docs/README_TH.md) | [Tiếng Việt](./docs/README_VI.md)

![Platform](https://img.shields.io/badge/Platform-iOS%2014.0%2B-black)
![Support](https://img.shields.io/badge/Support-TrollStore-blue)
![License](https://img.shields.io/badge/License-GPL--3.0-green)

> [![Join Telegram](https://img.shields.io/badge/Join-Telegram%20Channel-blue?logo=telegram&logoWidth=20&labelColor=26A5E4&color=white)](https://t.me/VansonMod)

---

## Introduction

**VansonMod** is an independent iOS debugging tool built for the **TrollStore** environment. It works externally instead of relying on traditional tweak injection, so many common workflows remain available on non-jailbroken devices, including process selection, memory search, memory browsing, pointer analysis and verification, signature analysis, scripting, and app archive management.

On jailbroken devices, VansonMod unlocks deeper code-level workflows such as **RVA patching** and **hardware watchpoint monitoring**. The current version has grown from a pure memory search utility into a broader iOS debugging workstation for both iPhone and iPad, with support for split view, landscape, and Stage Manager.

## Compatibility Notes

- **Available on TrollStore / non-jailbroken devices**: process selection, memory search, nearby search, result filtering, memory browsing, Hex editor, pointer analysis and verification, signature analysis, script tools, app archive management, and theme/language/icon settings.
- **Features that depend on the target task port**: some runtime features require successful access to the target process task port, so actual behavior can vary depending on the environment and target app state.
- **Recommended or limited to jailbroken environments**: `RVA Patch`, `RVA record management`, and `hardware watchpoint monitoring` are best used in **Dopamine / palera1n** style jailbreak environments.
- **Why**: on non-jailbroken devices, **AMFI** strictly enforces code-signing checks. Directly modifying the executable text segment (`__TEXT`) will usually crash the target app immediately.

## Language Support

- Built-in languages: 简体中文, 繁體中文, English, العربية, Deutsch, Español, Français, 日本語, 한국어, Português, Русский, ไทย, Tiếng Việt.

## Navigation

- **App Selection**: browse running processes, all installed apps, or system processes; search by name / Bundle ID / PID; quickly attach, open, kill, back up, or inspect code changes for a target app.
- **Memory Debug**: perform exact, fuzzy, group, range, and nearby searches, filter results, use the search timeline to restore earlier result snapshots, undo the last manual write, batch edit values, and jump into value or Hex views.
- **RVA Debug**: patch by module and offset, manage saved RVA records, and handle deeper code-level workflows in jailbreak environments.
- **Toolbox**: manage memory locks, favorites, pointers, RVA records, signatures, verifier files, and scripts in one place.
- **Settings**: configure theme, language, icons, tab order, search ranges, float tolerance, result limits, update checks, and more, with quick tab reordering by long-pressing the bottom menu.

## Highlights

- **Process and App Management**: supports `Running / All / System` views, localized app names, version display, starring, PID / Bundle ID copying, quick app launch, and process termination.
- **Memory Search and Batch Editing**: supports exact, fuzzy, group, range, and nearby search modes, result timeline snapshots with restore, manual-write undo, greater-than / less-than / between filters, fixed value writes, incremental edits, batch lock, batch favorite, and batch delete.
- **Memory Browser and Hex Editor**: supports address jumping, auto refresh, string view, and batch address copying; the Hex editor supports `Hex / Split / Text` layouts, row editing, offset jumps, and fast writes.
- **Pointer Analysis and Verification**: supports manual and automatic pointer chains, static / dynamic / all / backtrack modes, real-time verification, incremental snapshots, changed-region comparison, verifier file save/import/export, and lock integration.
- **Signature Analysis**: jump into signature analysis from any address, choose module scope, run global searches, apply smart masking, verify matches, and save signatures directly into the toolbox.
- **Script System**: includes a built-in JavaScript runtime with examples, shortcuts, and console output; script guides and examples can be viewed directly inside VM to help users get started faster.
- **RVA Debugging and Watchpoint Monitor**: supports module selection, offset patching, ARM64 instruction presets, and RVA record management; in jailbreak environments it also provides hardware watchpoint monitoring, hit records, a code inspector, and quick sending of hit locations into the RVA debugger.
- **App Archives and Process Audit**: supports one-tap backup and restore for `Documents / Library`, multiple archives, and Files app import/export; process audit helps you see which code locations or RVA values changed before and after the target app runs, with diff export and original-byte restore.
- **Settings and UX Improvements**: supports theme switching, language switching, app icon switching, tab reordering, quick tab reordering by long-pressing the bottom menu, fuzzy search range control, lock interval, prevent sleep, result limits, update checks, and native iPad split view, landscape, and Stage Manager support.

## Screenshots

v3.5 interface preview. All apps and data shown are demonstration examples.

| <div align="center"><img src="./Screenshots/APP_SELECT.PNG" width="100%" alt="Process selection"/></div> | <div align="center"><img src="./Screenshots/MEM_DEBUG.PNG" width="100%" alt="Memory debugging"/></div> | <div align="center"><img src="./Screenshots/MEM_BROWSER.PNG" width="100%" alt="Memory browser"/></div> | <div align="center"><img src="./Screenshots/MEM_HEX_MIX.PNG" width="100%" alt="Mixed Hex view"/></div> |
| :---: | :---: | :---: | :---: |
| <div align="center"><img src="./Screenshots/POINTER_ANALYSIS.PNG" width="100%" alt="Pointer analysis"/></div> | <div align="center"><img src="./Screenshots/POINTER_VERIFY.PNG" width="100%" alt="Pointer verification"/></div> | <div align="center"><img src="./Screenshots/POINTER_LOCKER.PNG" width="100%" alt="Pointer locking"/></div> | <div align="center"><img src="./Screenshots/RVA_MANAGER.PNG" width="100%" alt="RVA manager"/></div> |
| <div align="center"><img src="./Screenshots/SCRIPT_EDITOR.PNG" width="100%" alt="Script editor"/></div> | <div align="center"><img src="./Screenshots/SCRIPT_CREATE.PNG" width="100%" alt="Create a script"/></div> | <div align="center"><img src="./Screenshots/SETTINGS.PNG" width="100%" alt="Settings"/></div> | <div align="center"><img src="./Screenshots/SETTINGS_DARK.PNG" width="100%" alt="Settings in dark mode"/></div> |

---

## Related Project

Need a dylib edition for injected runtime workflows? See [VansonLoader](https://github.com/vaenshine/vansonloader), the companion dylib derivative of VansonMod.

---

## Changelog

See [Releases](https://github.com/vaenshine/VansonMod/releases).

---

## Installation

1. Download the latest `.tipa` from [Releases](https://github.com/vaenshine/VansonMod/releases).
2. Install it with **TrollStore**.
3. Launch the app, choose a target process, and start debugging.

---

## Build From Source

Requirements: Theos, Xcode command line tools, Python 3, `ar`, `tar`, `zip`, and `unzip`.

```sh
make clean package FINALPACKAGE=1 DEBUG=0
./scripts/release.sh
```

See [CONTRIBUTING](./CONTRIBUTING.md) for contribution rules and [SECURITY](./SECURITY.md) for private vulnerability reporting.

---

## Credits

*   Developer: **Vaenshine**
*   Special Thanks: **Gey1ist**, **Xiczee**, **Zoomin**
*   Community Support: [iOSGods.com](https://iosgods.com/)

---

## Disclaimer

This tool is intended for **security research, reverse engineering learning, and authorized technical testing**.

*   This project is open source under GPL-3.0. Paid redistribution is permitted when the distributor fully complies with GPL-3.0.
*   This tool is a general technical debugging utility. It does not ship with preset targets or custom operation schemes for specific apps.
*   Use this tool only in lawful, authorized environments and respect the rules that apply to target apps and systems.
*   Users are responsible for their operations and for resulting risks, including target app crashes, data loss or corruption, account restrictions, device instability, and legal liability.

---

## Important Statement

This project is open source under GPL-3.0. Development is driven by technical research and community exchange.

---

## License

GPL-3.0. See [LICENSE](./LICENSE).

## Distribution and Project Identity

Official VansonMod releases are published free of charge through this repository's [Releases](https://github.com/vaenshine/VansonMod/releases) page.

The project promotes free access and free sharing through official sources. The maintainer neither endorses nor recommends third-party paid resale of unchanged official packages. Such resale carries no official-channel or project-partner status. The redistribution rights granted by GPL-3.0 remain unchanged.

GPL-3.0 permits third parties to redistribute modified or unmodified copies for a fee. Distributors must satisfy all applicable GPL-3.0 requirements, including preservation of required notices, delivery of the license, access to the Complete Corresponding Source, and clear identification of modified versions.

The VansonMod name, logo, app icon, and official project identity remain protected project identifiers. Third-party distributors must clearly identify themselves as independent and unofficial and must avoid any presentation that suggests authorization, sponsorship, endorsement, or affiliation with the VansonMod project or its maintainer.

See [Trademark and Distribution Policy](./TRADEMARKS.md) for details.

---

## Star History

[![Star History Chart](https://api.star-history.com/chart?repos=vaenshine/VansonMod&type=date&legend=bottom-right&sealed_token=7GKlgSNa_RYfyFti6u-PKeTxObIt1P6yp9ExhaBjWXgxI78k9FV3xLprlOPWX_Rx4DkQRZ_ub-lWHoqPsTekAaDxkiZKMUhSqDuSCrqhTDn9cR8jQAE_pQ)](https://www.star-history.com/?repos=vaenshine%2FVansonMod&type=date&legend=bottom-right)
