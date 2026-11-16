# Dolphin-Huawei

A unified Android-focused Dolphin project for Huawei devices.

## Current build

The current build target is the pinned Official Dolphin Android app. MMJR2-VBI is included as a pinned reference source while compatible changes are reviewed and ported in small, testable patches.

**This is not yet a completed source-level merge of MMJR2-VBI.** The APK produced by the current workflow is the Official Dolphin base with this repository's build pipeline; it must not be described as containing MMJR2-VBI performance patches until those patches are actually ported and tested.

## Build an APK with GitHub Actions

1. Open the [Actions tab](https://github.com/zaydzaydfarhat-blip/dolphin-huawei/actions).
2. Select **Android APK**.
3. Press **Run workflow** and choose the `main` branch.
4. When the run succeeds, open it and download the `dolphin-huawei-android-debug` artifact.

The workflow builds the Android debug APK from the Official Dolphin source and uploads it as a downloadable artifact. The first build can take a while because it compiles Dolphin's native C++ code.

## Source layout

- `Source/` — Official Dolphin source, pinned to `19018c423998eea431c2c435903b3c97597d0768`.
- `upstream/MMJR2-VBI/` — MMJR2-VBI reference source, pinned to `396014bc1712a001597d25ee849a5253fc170180`.
- `patches/` — reviewed changes ported into the Official Dolphin base.
- `docs/` — integration plan and test checklist.

Clone with submodules:

```sh
git clone --recurse-submodules https://github.com/zaydzaydfarhat-blip/dolphin-huawei.git
cd dolphin-huawei
```

If already cloned:

```sh
git submodule update --init --recursive
```

## Integration strategy

Official Dolphin remains the build base so its current Android input, storage, homebrew, and networking features are not replaced by older code. MMJR2-VBI is based on an older Dolphin generation, so its changes must be ported selectively.

Huawei-specific GPU tuning is experimental until it is measured on real Huawei hardware. No device-specific performance improvement is claimed yet.

## Upstreams and licensing

- [Official Dolphin](https://github.com/dolphin-emu/dolphin)
- [Dolphin MMJR2-VBI](https://github.com/Medard22/Dolphin-MMJR2-VBI)

Dolphin is GPLv2-or-later. Preserve upstream copyright, license, and attribution notices in derivative builds. See the upstream repositories for their complete license files.
