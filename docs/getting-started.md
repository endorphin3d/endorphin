---
layout: default
title: Getting Started
nav_order: 1
permalink: docs/getting-started
has_toc: false
---

{% capture preface %}
The Endorphin uses a slightly different belt setup from the original Ender 5, known as a "Markforged kinematic" or Hybrid CoreXY. In this setup the X belt moves like a CoreXY but the Y axis remains in its original Ender 5 cartesian setup--one of the main reasons why the Endorphin is is so much faster to build than a CoreXY conversion.
{% endcapture %}
{% include docs-preface.html
  title="# Getting Started"
  image="/assets/images/docs/getting-started/belt-path.png"
  alt="Belt path"
  content=preface
%}

{% capture kinematic %}
Now, if you know anything about CoreXY machines you know that unlike cartesian printers, CoreXY printers don't have an "X stepper" or a "Y stepper" because a movement of one stepper affects both belts. In the Markforged kinematic, this is only partially the case:

- The X stepper can move the printhead along the X axis by simply moving its belt while the Y belt stays stationary
- The Y stepper only has to worry about moving the gantry linearly along the Y axis (cartesian style)
- BUT when the Y stepper moves the gantry, the length of the X belt on either side of the gantry is affected and thus the X stepper must also move to compensate

Luckily this kinematic is supported by both Klipper and the stock Marlin firmware (with a small modification).
{% endcapture %}
{% include docs-step.html
  heading="#### Motion Diagram"
  image="/assets/images/docs/getting-started/kinematic.png"
  alt="Kinematic"
  content=kinematic
%}

## Software

{: .warning }
Don't make these configuration changes until *AFTER* you've printed out all the parts for at least stage 1! You need a working printer (or a second printer) to get stage 1 off the ground.

### Klipper

If you've been thinking about making the leap to Klipper, this might be the push you've been needing. Making config changes to a machine running Klipper is roughly 1000% easier than Marlin. All that's required to configure Klipper to use the new kinematic is editing `printer.cfg` and changing `kinematics` under the `[printer]` section:

```yml
[printer]
kinematics: hybrid_corexy
...
```

Now save and restart and you're done. Seriously, you're done. You can skip on to the [next page](/docs/stages) now.

### Marlin (Original Firmware)

The Marlin firmware is a bit trickier. To change the kinematics here you need to recompile and flash the firmware on your board.

Start by following the instructions on the [Marlin site](https://marlinfw.org/docs/basics/install_platformio_vscode.html) until you reach the section on example configurations where you're told to "find the configuration files for your printer." Assuming you've downloaded the Marlin configurations, you'll now need to pick the folder that corresponds to your printer + board version. The surest way to figure which board you have is to open up the case and check. If you have a 4.2.7 or a 4.2.2, it'll be printed right under the Creality logo in the center of the board. If you have a v1 board, there will be no version printed at all.

![Endorphin stage 1](/assets/images/docs/getting-started/board.png)

So for example if you have an Ender 5 Pro with a 4.2.7 board, you'll find the correct configuration in the folder `config/examples/Creality/Ender-5 Pro/CrealityV427`.

Next we need to configure the firmware to use the Markforged kinematic. This only requires editing a single line in the `Configuration.h` file. If you search the file for "MARKFORGED_XY" you should see this line several hundred lines down:

```c
//#define MARKFORGED_XY
```

You'll want to un-comment this line, like so:

```c
#define MARKFORGED_XY
```

Now you can continue following the Marlin guide on compiling the new firmware. Once you've compiled, you can put the new firmware file (usually `firmware.bin`) at the root of your microSD card. Just to be 100% certain the printer will recognize the new firmware, rename the file to `firmware-endorphin.bin`. Then with your printer powered off, insert the SD card and power the printer on. Wait a few minutes to ensure the install finishes, then power the printer down and remove the card. Delete `firmware-endorphin.bin` and you're done!

---

[Next →](/docs/stages){: .btn .btn-outline .fs-5 }