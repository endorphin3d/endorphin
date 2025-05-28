---
layout: default
title: Introduction
nav_order: 1
permalink: docs
has_toc: false
---

{% capture preface %}
In the last few years 3D printers have become blisteringly fast, pushing the limits of both heating and cooling while leaving those of us with printers like the Ender 5 feeling a bit left out of the fun. That ends now. Your Ender 5 is capable of being every bit as fast as a Voron without the hefty price tag. There have been [other](https://zerog.one) CoreXY [projects](https://www.printables.com/model/169131-ender-5-core-xy-with-linear-rails-mk3) to do a full conversion on the Ender 5, but often the price of parts or the complexity of the build makes it hard to justify over just buying something pre-built like a Bambulab P1P.

**The Endorphin is different.**

With a first-stage build you can do in an afternoon with parts that total less than $25, you no longer have any excuses *not* to turn Ender 5 into a speed demon.
{% endcapture %}
{% include docs-preface.html
  title="# Introduction"
  image="/assets/images/docs/getting-started/belt-path.png"
  content=preface
%}

{% capture kinematic %}
The Endorphin uses a slightly different belt setup from the original Ender 5, known as a "Markforged kinematic" or Hybrid CoreXY. In this setup the X belt moves like a CoreXY but the Y axis remains in its original Ender 5 cartesian setup.

### Why Though?

The basic idea is this: The less weight being thrown around, the faster the printer's acceleration/deceleration can be. Less weight also means higher top speeds because there will be less energy required to stop and change direction at the end of each move. This is why the CoreXY setup has become the choice of pretty much all high-speed printers such as the BambuLab, Voron, Ratrig, and HevORT.

This project moves the X stepper motor off the gantry and onto the frame, where the Y steppers won't have to lug it around anymore. This is a significant amount of weight we're saving!

Now, if you know anything about CoreXY machines you know that unlike cartesian printers, CoreXY printers don't have an "X stepper" or a "Y stepper" because a movement of one stepper affects both belts. In the Markforged kinematic, this is only partially the case:

- The X stepper can move the printhead along the X axis by simply moving its belt while the Y belt stays stationary
- The Y stepper only has to worry about moving the gantry linearly along the Y axis (cartesian style)
- BUT when the Y stepper moves the gantry, the length of the X belt on either side of the gantry is affected and thus the X stepper must also move to compensate

### Firmware

Luckily this kinematic is supported by both Klipper and the stock Marlin firmware (with a small modification). After you've printed the parts for at least stage 1, just follow the instructions in the [firmware section](/docs/firmware) to use the new kinematic.
{% endcapture %}
{% include docs-step.html
  heading="## Kinematic"
  image="/assets/images/docs/getting-started/kinematic.png"
  content=kinematic
%}

## Q&A

### What about the Ender 5 Plus?

Yes, as of version 1.1 the 5+ is also fully supported. Just make sure you don't leave slack in the X belt because that's a *long* belt path.

---

[Next →](/docs/stages){: .btn .btn-outline .fs-5 }
