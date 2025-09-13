# About This Project

Hello everyone!  
This is a 12V/5V 8A adjustable buck converter I designed for a design team (96W Converter on a good day).

![Buck Converter 3D Render](<Buck Convertor (12V 6A)-1.png>)

This version of the board is untested, but the core functionality (the converting) has been tested and it works pretty well.

## JLC Note

Every component on the board has a JLC#.  
You just need to solder your own automotive blade fuse holder (3557-2) and Molex Mini Fit Jrs (1726480102)—**though these connectors and the fuse holder can technically also be assembled by JLC, just at additional expense**.  
Approximate cost is ~40 CAD for 2 boards assembled, 2 week shipping, but could vary.

## Connector Note

It's a little tricky crimping those, but you can do it with a basic JST crimper.

## Other Functionality

- Automotive blade fuse and a PFET for reverse polarity protection present  
- Gold fingers for a slot card mount  
- Core chip: SIC438BED-T1-GE3 (large package, but JLC can assemble it with no problem)

# Tested Functionality

- 12V 6A works at 300 kHz switching frequency (Vin: 13.2V) with a thermal rise of about ~25°C  
- 5V 6A works at 750 kHz switching frequency (Vin: 13.2V) with a thermal rise of about ~10°C  
- Tests conducted with an electronic load, varying the current, and measuring temperature with a thermocouple  
- For higher voltage input: use 750 kHz for the 12V rail (calculate max duty cycle using the SIC438BED-T1-GE3 datasheet)

# Untested Functionality

- Reverse polarity protection was only simulated in MultiSim—untested in hardware due to costs  
- Jumpers for swapping 12V/5V and switching frequency are untested (just resistor swapping, so risk is minimal)  
- Board theoretically runs at 8A (no OCP trip at full load, chip rated 8A), but output ripple and full thermal capability aren't fully characterized. **Use at your own risk.**

# Things To Clean Up

- All JLC component footprint references are messed up because of a switch to KiCad 9  
- 3D models for all components need to be added eventually (on the todo list)  
- Better test pad layout is coming in a future revision  
- Replace the PFET with a proper reverse polarity charge pump IC for a high-side NFET (lower Rds(on), less heat)  
- Want different connectors? Let me know, or just mod the files yourself—they're on the page!

# Schematic

![Schematic Diagram](image.png)

# Final Remarks

- 2-layer board build *might not work*—JLC assembly doesn't support this IC on 2 layer builds (success rate ~10%)  
- 4-layer assembly has been issue-free so far  
- If you want to fund more testing, DM me on Discord @javezki

Love y'all
