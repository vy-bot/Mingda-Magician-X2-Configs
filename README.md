# Mingda-Magician-X2-Configs
Cura profile and configs for Mingda Magician X2 3D printer.

Didn't find any yet, so here you go, hope someone finds it useful.


Pritner specs needed for most slicers:

Name: Magician X2

Print Width: 230.0 mm
Print Depth: 230.0 mm
Print Height: 260.0 mm

G-code flavor: Marlin (2)

# Start G-Code
[code]

M104 S180 ; Start pre-heating the nozzle to a safe temperature where the filament won't ooze to save time
M190 S{material_bed_temperature_layer_0} ; Start heating the bed to the target temperature specified in Print Settings and wait until the temperature is reached
G92 E0 ; Reset extruder
G28 ; Auto Home all axes
M420 S1 ; Automatic bed leveling with saved mesh
M104 S{material_print_temperature_layer_0} ; Start heating the nozzle to the target temperature specified in Print Settings
G1 Z2.0 F3000 ; Move Z Axis up
G1 X0.1 Y20 Z0.3 F5000.0 ; Move to start position
M109 S{material_print_temperature_layer_0} ; Wait until the nozzle is heated to the target temperature specified in Print Settings

# End G-Code
[code]
M104 S0
M140 S0
;Retract the filament
G92 E1
G1 E-1 F300
G28 X0 Y0
G1 Y220
