# Dolphin-Huawei

A combined Android-focused Dolphin project for Huawei devices.

## Goal

Use current **Official Dolphin** as the base, then selectively port useful Android performance and compatibility work from **Dolphin MMJR2-VBI**. The target is one emulator that keeps Official Dolphin's current Android input, homebrew, and networking support while evaluating MMJR2-VBI's performance work.

Huawei-specific changes must be measured on real Huawei hardware. No Maleoon 910 optimization is claimed until it is implemented and tested.

## Source layout

- `Source/` — Official Dolphin source, pinned to `19018c423998eea431c2c435903b3c97597d0768`.
- `upstream/MMJR2-VBI/` — MMJR2-VBI reference source, pinned to `396014bc1712a001597d25ee849a5253fc170180`.
- `patches/` — reviewed, isolated ports that will be applied to the Official Dolphin base.
- `docs/` — source audit and porting notes.

Clone with submodules:

```sh
git clone --recurse-submodules https://github.com/zaydzaydfarhat-blip/dolphin-huawei.git
cd dolphin-huawei
```

If already cloned:

```sh
git submodule update --init --recursive
```

## Important status

This commit establishes reproducible references to both upstream projects. **It is not yet a merged emulator build**: MMJR2-VBI changes will be reviewed and ported individually so older code does not overwrite newer Official Dolphin functionality. APK builds should be enabled after the first compatible code ports are in place.

## Upstreams

- [Official Dolphin](https://github.com/dolphin-emu/dolphin)
- [Dolphin MMJR2-VBI](https://github.com/Medard22/Dolphin-MMJR2-VBI)

Both upstream projects are distributed under GPL-family terms. See their own license and notice files; preserve all copyright and attribution notices in any derivative distribution.
