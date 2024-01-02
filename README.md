# Mingda-Magician-X2-Configs
Cura profile and configs for Mingda Magician X2 3D printer.

Didn't find any yet, so here you go, hope someone finds it useful.

Download Slicer here: https://ultimaker.com/software/ultimaker-cura/

Printer specs needed for most slicers:

```
Name: Magician X2

Print Width: 230.0 mm
Print Depth: 230.0 mm
Print Height: 260.0 mm

Print Head:
- X min -25 mm
- Y min -60 mm
- X max 60 mm
- Y max 25 mm
- Gantry Height 25 mm

G-code flavor: Marlin (2)
```

# Cura Slicer Start G-Code
```
M104 S{material_print_temperature_layer_0} ; heat the nozzle
G28 ; Auto Home all axes
M420 S1 ; Automatic bed leveling
G92 E0 ; Reset extruder
G1 X0.1 Y20 Z0.5 F1000.0 ; Move to start position
M190 S{material_bed_temperature_layer_0} ; heat the bed
M117 ; Purge extruder
G92 E0 ; reset extruder
G1 Z1.0 F3000 ; move z up little to prevent scratching of surface
```

# Cura Slicer End G-Code
```
G92 E1 ;Retract the filament
G91; relative positioning
G1 Z1.0 F1000 ; move z up little to prevent scratching of print
G90; absolute positioning

M104 S0; turn off extruder
M140 S0 ; turn off bed

G1 Y225 F1000; move the bead foward
G28 X0 Y0

M84 ; disable motors
M420 S0; deactivate the automatic bed leveling
M106 S0 ; turn off fan
```
