# Changelog

All notable changes to **HaloPoint 3.0** are documented here.


### Added
- 2026-06-26 -- Laplacian orientation distribution (`Laplacian = 2`), CPU and GPU paths. Suggested by Marko Riikonen and inspired by Jiajie Zhang (LoveDaisy).

### Changed
- 2026-06-28 -- Multi-select histogram in the raypath report window: `_activeBin` (crystal
  canvas + which-ray combo) is now separate from `_selectedBins` (dot
  highlighting). Selection mode set to `Extended`. Multiple paths can be selected at once by holding Ctrl or Shift while clicking rows, in which case the highlighted dots are the union of all selected paths, while the crystal illustration and Ray dropdown continue to follow the most recently clicked row.

### Fixed
- 2026-06-27 -- Colatitude sampler restricted output to [90°, 180°] on both CPU and GPU paths; now covers the full [0°, 180°] range.
- 2026-06-27 -- C6 symmetry filter on the GPU recording path now matches the CPU result.
- 2026-06-27 -- Hidden-line raypath illustration renderer: occlusion splitting was applied
  before the halo-cut pass, producing incorrect edge cuts; splitting is now
  deferred until after the cut pass.

### Known issues
- GPU recording with a non-convex primary crystal produces a correct halo image
  but records no per-face encounter detail for that crystal.
- Multiple scattering combined with non-convex crystals, and recording combined
  with multiple scattering, fall back to the CPU engine.


