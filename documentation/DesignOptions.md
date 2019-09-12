### Mainboard
Currently there are two designs being discussed:
1. Raspbery Pi (or Beagle with HDMI?) based solution - A hat/cape for the SBC would control a Stepper motor, LED array, fans, and endstop. 
An HDMI to MIPI adapter will be used to control the print screen.
2. A All-In-One control board - Similar to the one provided by CBD. The board would have a microcontroller to handle the 
Stepper motor, LED array, fans, and endstop. It would have an FPGA to control the print screen.

### HDMI to MIPI options
- https://www.aliexpress.com/item/32798469290.html
- https://www.aliexpress.com/item/32988260420.html

### Stepper driver options
- Trinamic 2209 Pros(noiseless, ability to run without endstops)
  - https://www.trinamic.com/products/integrated-circuits/details/tmc2209-la/
  - Pros: noiseless, ability to run without endstops, uart configurable
- Trinamic 5160 
  - https://www.trinamic.com/products/integrated-circuits/details/tmc5160/
  - Pros: cooler operation, higher amps, more torque
  - Cons: overkill, twice the price expensive

### LED options
- EPAX parallel 50W (will need cooling - see below)
  - https://epax3d.com/products/parallel-matrix-mod-for-epax-x1
- #LCDCoollingResearch FB hashtag to various bits posted there:
  - https://www.facebook.com/hashtag/lcdcoolingresearch

### FPGA options
- Xylinx has good options.  This demo was an IEEE webinar on driving high res displays "for pennies":
  - https://www.youtube.com/watch?v=oq69AQkUWbU&feature=youtu.be


### Input Voltage options
- 12V
  - Pros: Easier to find parts like fans
- 24V
  - Pros: higher torque on stepper motor, less current to get same power means smaller guage wire needed.
