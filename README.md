# KlipperScreen With Modfied shutdown.py 

Changed the shutdown button to power off a power device setup in moonraker.conf and printer.cfg. 

Example Using for BBT Manta M8P with CB1 and BTT Relay. 
```
-------add to to printer.cfg-----
[output_pin _power]
pin: PD14
value: 1
shutdown_value: 1

[gcode_macro SHUTDOWN]
gcode:
  SET_PIN PIN=_power VALUE=0
  {action_call_remote_method("shutdown_machine")} 

-------add to to moonraker.conf-----

[power Qidi X-CF Pro]
type: klipper_device
object_name: gcode_macro SHUTDOWN
# The option below locks out requests to toggle the flare
# when Klipper is printing, however it cannot prevent a
# direct call to the SET_FLARE gcode macro.
locked_while_printing: True

```

KlipperScreen is a touchscreen GUI that interfaces with [Klipper](https://github.com/Klipper3d/klipper) via [Moonraker](https://github.com/arksine/moonraker). It allows you to switch between multiple printers and access them from a single location. Notably, it doesn't need to run on the same host as your printer; you can install it on another device and configure the IP address to connect to the printer.

### Documentation

For detailed information, [click here to access the documentation](https://klipperscreen.github.io/KlipperScreen/).

### Inspiration

KlipperScreen draws inspiration from [OctoScreen](https://github.com/Z-Bolt/OctoScreen/) and was developed to provide a native touchscreen GUI compatible with [Klipper](https://github.com/Klipper3d/klipper) and [Moonraker](https://github.com/arksine/moonraker).

[![Main Menu](docs/img/panels/main_panel.png)](https://klipperscreen.readthedocs.io/en/latest/Panels/)

Explore more screenshots [here](https://klipperscreen.readthedocs.io/en/latest/Panels/).

### Translations

Translations for KlipperScreen are hosted on Weblate. Thanks to the Weblate team for supporting the open-source community.

<a href="https://hosted.weblate.org/engage/klipperscreen/">
    <img src="https://hosted.weblate.org/widget/klipperscreen/svg-badge.svg" alt="Translation status" />
</a>

Click the widget below to access the translation platform:

<a href="https://hosted.weblate.org/engage/klipperscreen/">
    <img src="https://hosted.weblate.org/widget/klipperscreen/horizontal-auto.svg" alt="Weblate widget" width="50%" />
</a>

### About the Project

KlipperScreen was created by Jordan Ruthe in 2020.

| Donate to Jordan |
|------------------|
| [Patreon](https://www.patreon.com/klipperscreen) |
| [Ko-fi](https://ko-fi.com/klipperscreen) |

Since 2021, the project has been maintained by Alfredo Monclus (alfrix).

| Donate to Alfrix |
|------------------|
| [Ko-fi](https://ko-fi.com/alfrix) |

We extend our gratitude to all contributors who have helped along the way. [Meet the contributors](https://github.com/KlipperScreen/KlipperScreen/graphs/contributors).

### Sponsors

![LDO](docs/img/LDO-LOGO_SQ.png) ![YUMI](docs/img/YUMI.png)

Special thanks to [LDO](https://ldomotors.com/) and [YUMI](https://wiki.yumi-lab.com/) for sponsoring KlipperScreen and the open-source community.
