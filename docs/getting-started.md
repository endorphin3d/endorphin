---
layout: default
title: Getting Started
nav_order: 1
permalink: docs/getting-started
has_toc: true
---

## Software

You might have noticed from the pictures that the Endorphin uses a slightly different belt setup from the original Ender 5, but it's not exactly a CoreXY either. This is known as the "Markforged kinematic" or a "Hybrid CoreXY" and is the central idea behind the Endorphin which allows us the benefits of a CoreXY with far less modification (more on that later). Luckily this kinematic is supported by both Klipper and the stock Marlin firmware with a small modification.

{: .warning }
Don't make these configuration changes until *AFTER* you've printed out all the parts for at least stage 1! You need a working printer (or a second printer) to get stage 1 off the ground.

### Klipper

If you've been thinking about making the leap to Klipper, this might be the push you've been needing. Making config changes to a machine running Klipper is roughly 1000% easier than Marlin. All that's required to configure Klipper to use the new kinematic is editing `printer.cfg` and changing `kinematics` under the `[printer]` section:

```yml
[printer]
kinematics: hybrid_corexy
...
```

Now save and restart and you're done. Seriously, you're done.

### Marlin (Original Firmware)

The Marlin firmware is a bit trickier. To change the kinematics here you need to recompile and flash the firmware on your board.

Start by following the instructions on the [Marlin site](https://marlinfw.org/docs/basics/install_platformio_vscode.html) until you reach the section on example configurations where you're told to "find the configuration files for your printer." Now you'll need to pick the folder that corresponds to the printer + board version. The surest way to figure which board you have is to open up the case and check. If you have a 4.2.7 or a 4.2.2, it'll be printed right under the Creality logo in the center of the board. If you have a v1 board, there will be no version printed at all.

![Endorphin stage 1](/assets/images/docs/getting-started/board.png)

So for example if you have an Ender 5 Pro with a 4.2.2 board, you'll find the correct configuration in the folder `config/examples/Creality/Ender-5 Pro/CrealityV422`.

Next we need to configure the firmware to use the Markforged kinematic. This only requires editing a single line in the `Configuration.h` file. If you search the file for "MARKFORGED_XY" you should see this line several hundred lines down:

```c
//#define MARKFORGED_XY
```

You'll want to un-comment this line, like so:

```c
#define MARKFORGED_XY
```

Now you can continue following the Marlin guide exactly as you normally would. Once you've compiled, you can put the new firmware file (usually `firmware.bin`) at the root of your microSD card. Just to be 100% certain the printer will recognize the new firmware, rename the file `firmware-endorphin.bin`. Then with your printer powered off, insert the SD card and power the printer on. Wait a few minutes to ensure the install finishes, then power the printer down and remove the card. Delete `firmware-endorphin.bin` and you're done!