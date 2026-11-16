# Dolphin-Huawei integration plan

## Pinned upstream snapshots

| Role | Repository | Branch | Commit |
|---|---|---|---|
| Base | dolphin-emu/dolphin | master | 19018c423998eea431c2c435903b3c97597d0768 |
| Reference | Medard22/Dolphin-MMJR2-VBI | rolling-dev | 396014bc1712a001597d25ee849a5253fc170180 |

## Integration strategy

1. Keep current Official Dolphin as the only build target and source of truth.
2. Compare MMJR2-VBI changes by subsystem, starting with JIT/CPU, vertex loading, DSP, graphics pipeline, and VBI Skip.
3. Port only changes that apply cleanly to the current code and do not regress Official Dolphin's Android input, storage, networking, or homebrew support.
4. Keep WiiLink/WiiConnect24 behavior and its settings intact; test it independently from performance changes.
5. Add Huawei-specific tuning only when it is supported by device measurements on the Kirin 9000WE / Maleoon 910 target.
6. Add the Android APK workflow after the first source changes compile successfully.

## Known compatibility gap

MMJR2-VBI's published source line is based on Dolphin 2407-era code, while the selected Official Dolphin base is much newer. This is why the project uses a selective port rather than replacing the current source tree with the older fork.

## Test checklist

- Android arm64 debug build
- Launch and game list
- GameCube and Wii boot
- Controller and touch input
- Homebrew app launch
- Wii networking / WiiLink configuration
- Mario Kart Wii performance and frame pacing on the target Huawei tablet
- Shader-cache warm-up versus steady-state performance
- Thermal behavior over a sustained session
