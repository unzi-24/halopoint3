# Changelog

All notable changes to **HaloPoint 3.0** are documented here.


### Added
- 2026-07-07 -- Precise crystal rotation controls in the raypath report window: two sliders (`Horizontal` for ZRot, `Vertical` for YRot) rotate the crystal by exact angles, staying in sync with mouse-drag rotation. Arrow keys step 0.01°, mouse wheel over a slider steps 0.01°, and track clicks / PageUp-Down step 0.1°.
- 2026-07-07 -- Save Image button in the analysis window: exports the full-resolution sky view as PNG, TIFF, or BMP, including the turquoise highlight dots/rings and the measurement stick with its label when present. Complements the existing HTML export for when the analysis image is wanted on its own.
- 2026-07-05 -- Two new celestial points added to the Image Center dropdown list, namely  `Horizon, sunside` and `Horizon, opposite side`.
- 2026-06-26 -- Laplacian orientation distribution (`Laplacian = 2`), CPU and GPU paths. Suggested by Marko Riikonen and inspired by Jiajie Zhang (LoveDaisy).

### Changed
- 2026-06-28 -- Multi-select histogram in the raypath report window: `_activeBin` (crystal canvas + which-ray combo) is now separate from `_selectedBins` (dot highlighting). Selection mode set to `Extended`. Multiple paths can be selected at once by holding Ctrl or Shift while clicking rows, in which case the highlighted dots are the union of all selected paths, while the crystal illustration and Ray dropdown continue to follow the most recently clicked row.

### Fixed
- 2026-07-04 -- Pyramid apex angle was restricted to 0-90 degrees; now values beyween 0.001 and 179.999 are allowed.
- 2026-06-27 -- Colatitude sampler restricted output to [90°, 180°] on both CPU and GPU paths; now covers the full [0°, 180°] range.
- 2026-06-27 -- C6 symmetry filter on the GPU recording path now matches the CPU result.
- 2026-06-27 -- Hidden-line raypath illustration renderer: occlusion splitting was applied before the halo-cut pass, producing incorrect edge cuts; splitting is now deferred until after the cut pass.

### Known issues
- GPU recording with a non-convex primary crystal produces a correct halo image but records no per-face encounter detail for that crystal.
- Multiple scattering combined with non-convex crystals, and recording combined with multiple scattering, fall back to the CPU engine.


