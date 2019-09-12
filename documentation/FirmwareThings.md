## Firmware brainstorm wish functions

### Globals
- Set zero
- Zero offset
- Cascade style failsafe settings (File globals / file local overrides / Machine defs / user exposure overides or offsets)
- Print Mode 3D,2D

### Layers
- Machine default Layer settings
- Global default layer height/exposure
- Absolute override of H/E
- Relative override of H

### Display
- Configurable for multiple sizes/resolutions (5.5" 2560x1440, 8.9" 2560x1600, 5.5" 4k, 10.1" 4k)
- Create and apply full-resolution illumination mask based on input screen intensity tiff.
- Consider ways to drive display without the bloat of X11
  - https://en.wikipedia.org/wiki/OpenMAX
  - https://jogamp.org/jogl-demos/www/
  
### File parser
- Ability to run a print with only a zip of images
- Ability to read standard and common formats (cws, zip, cbddlp, photon, spark, SL1)
- Plugabble new file formats

