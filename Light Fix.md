A fix for case lights in Fluidd (web interface) on the Elegoo Neptune 4 from the Elegoo Discord

Unfortunately i was unable to find the ideal fix because i wanted to control the lights using the XXXXXXXX in fluidd instead of a macro but using a macro is better than no light control
I may update this in the future to also include separate macros for just turning off or on the light
#####################################################################
# LED Control
#####################################################################
# LED Control 1.0
[output_pin caselight]
pin: PB7
pwm: false
shutdown_value:0
value:0.0

[output_pin caselight1]
pin: PC7
pwm: false
shutdown_value:0
value:0.0


# LED Control 2.0
[gcode_macro FLASHLIGHT_SWITCH]
description: Switch Hotend LEDs
gcode:
  RUN_SHELL_COMMAND CMD=FLASHLIGHT

[gcode_shell_command FLASHLIGHT]
command: sh /home/mks/sled2.sh
timeout: 5.

[gcode_macro MODLELIGHT_SWITCH]
description: Switch Logo LEDs
gcode:
  RUN_SHELL_COMMAND CMD=MODLELIGHT

[gcode_shell_command MODLELIGHT]
command: sh /home/mks/sled1.sh
timeout: 5.
