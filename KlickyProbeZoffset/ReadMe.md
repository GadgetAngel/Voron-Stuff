
# Klicky Probe as Endstop
## Benefits
1. Any buildplate thickness
2. Only one variable: Nozzle to switch distance, instead of z-endstop pin, switch body and nozzle
3. Easy to set up

## Drawbacks
1. Your z-offset will change when you swap nozzles. This is the only time you have to recalibrate z-offset
2. No Automatic Z-Offset possible
## How to set up
1. Open your klicky-variables.cfg
2. Replace the following lines:
`variable_z_endstop_x: 1000`
`variable_z_endstop_y: 1000`
with 
`variable_z_endstop_x: 0`
`variable_z_endstop_y: 0`
3. Open your printer.cfg
4. Comment out or Replace in `[stepper_z]`
`endstop_pin: `
with 
`endstop_pin: probe:z_virtual_endstop`

5. Comment out `position_endstop`
6. Set your probe offsets in `[probe]` section
	`x_offset: 0`
	`y_offset: 19.75`
`z_offset: 6.42`

7. Calibrate your z-offset the old fashioned paper way. Make sure to `SAVE TO PROBE` and not `SAVE TO ENDSTOP`
8. Enjoy :) 

## Important Notes & Tips
1. Always test your freshly set up z offset on the outer edges of your print surface. Incase anything goes wrong, you will only scratch the edge and not the middle. 
2. Your z-offset will change when you swap nozzles. This is the only time you have to recalibrate z-offset
3. 