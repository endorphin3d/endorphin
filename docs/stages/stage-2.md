---
layout: default
title: Stage 2
nav_order: 2
parent: Stages
permalink: docs/stages/stage-2
---

{% capture preface %}
> The goal of this stage is to drop the next heaviest parts on the X carriage: The V-slot wheels and steel mounts. This will yield us another **270g** of moving weight reduction--that's another half pound!
{: .fs-5 .fw-300 .text-grey-dk-100 .text-justify }
{% endcapture %}
{% include docs-preface.html
  title="# Stage 2: Linear Y Rails"
  image="/assets/images/docs/stages/stage-2/stage-2-render-lg.png"
  content=preface
%}

---

## Bill Of Materials

#### Linear Rails

| Size              | Length | Quantity | Link                                                                                                                                                                                      |
| :---------------- | :----- | :------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MGN12H Rail+Block | 300mm  | 2        | [Amazon](https://www.amazon.com/gp/product/B09QPCTYDM), [Fabreeko](https://www.fabreeko.com/collections/honeybadger/products/honeybadger-mgn12h-black-steel-rails?variant=43180991545599) |

#### Bolts

| Part             | Type              | Quantity | Link                                                   |
| :--------------- | :---------------- | :------- | :----------------------------------------------------- |
| M3x8 socket head | ISO 4762, DIN 912 | 20       | [Amazon](https://www.amazon.com/gp/product/B08R3GJGWT) |

#### T-Nuts

| Size           | Quantity | Link                                                   |
| :------------- | :------- | :----------------------------------------------------- |
| M3 2020 T-nuts | 12       | [Amazon](https://www.amazon.com/gp/product/B08NZMD2BJ) |

---

{% capture printing %}
**STL files for this stage are** [here](https://github.com/endorphin3d/endorphin/tree/main/STLs/stage-2)

The right Y rail mount is best printed on its side, but you'll need to make sure your bridge and support settings are dialed in pretty well to prevent sagging and any support interface being left behind (the tolerances for the aluminum extrusion are pretty tight on purpose).

The left mount can be printed in the same orientation *or* on its back. While this makes it easier to print and get correct tolerances against the aluminum extrusion, the strength at the belt attachment points is theoretically lower than being printed on the side.

{: .text-justify }
{% endcapture %}
{% include docs-step.html
  heading="## Printing"
  image="/assets/images/docs/stages/stage-2/plating.png"
  content=printing
%}

{: .note }
A great help in mounting the rails is a [rail alignment tool](https://www.thingiverse.com/thing:3533580). There are several other similar alignment tools on Thingiverse and Printables if you don't like this one. You'll want to print this tool before beginning the next step.

{% capture left %}
1. Loosen the X and Y belts then slide the Y belts out of the wheel plates. You won't be able to reuse these belts so you can toss them.
1. Remove the v-slot wheel screws and wheels on the left wheel plate
1. Remove the two M5 screws on the underside of the plate which attach it to the X gantry and **save these for later**
1. The plate can now be removed from the gantry
1. Using M3x8 screws and T-nuts, secure the MGN12 rail to the **outside** of the frame (this is where the alignment tool comes in handy)
1. Attach your new left linear mount (the smaller of the two) to the linear bearing block (the slidey thing) using M3x8 screws
1. Press the X gantry into the 20mm cutout in the mount then use one of the M5 screws from step 3 to secure mount to the X gantry from the underside
1. Fish one end of the Y belt through from the top of the new rail mount, then out the bottom and back in the direction it orginated
1. Secure the belt against its own teeth using a zip tie or [belt clip](https://raw.githubusercontent.com/endorphin3d/endorphin/main/STLs/stage-3/belt_clip-touthed.stl) designed by the [VzBot team](https://github.com/VzBoT3D/Vz-Printhead-Printed).

{% endcapture %}
{% include docs-step.html
  heading="## Left Rail"
  video="/assets/vids/docs/stages/stage-2/assembly-left-linear-y.mp4"
  content=left
%}

{% capture right %}
1. Remove the v-slot wheel screws and wheels on the right wheel plate
1. Remove the two screws on the underside of the plate which attach it to the X gantry and save one of these screws for later
1. The plate can now be removed from the gantry
1. Remove the center idlers and the sandwich blocks. You won't be needing the bottom block but the top one will be reused.
1. Using M3x8 screws and T-nuts, attach the MGN12 rail to the **outside** of the frame (again, using the alignment tool)
1. Attach your new right linear mount to the linear bearing block using M3x8 screws
1. Press the X gantry into the 20mm cutout in the mount then use one of the M5 screws from step 2 to secure mount to the X gantry from the underside
1. Reattach the center idlers as the were before, minus the bottom block. **Don't forget the M3 washers on both sides of the pulleys!**
1. Fish one end of the Y belt through from the top of the new rail mount, then out the bottom and back in the direction it orginated
1. Secure the belt against its own teeth using a zip tie or belt clip

{% endcapture %}
{% include docs-step.html
  heading="## Right Rail"
  video="/assets/vids/docs/stages/stage-2/assembly-right-linear-y.mp4"
  content=right
%}

## Optional Upgrades

{% capture ytensioner %}
While your Y belts are off why not give yourself a nice modern tensioner on the left side like you have on the right?

The design is exactly the same as the right tensioner, so you just need to print a second [knob](https://raw.githubusercontent.com/endorphin3d/endorphin/main/STLs/stage-1/tensioner-knob.stl) and [slider](https://raw.githubusercontent.com/endorphin3d/endorphin/main/STLs/stage-1/tensioner-slider.stl) from stage 1 plus the [tensioner housing](https://raw.githubusercontent.com/endorphin3d/endorphin/main/STLs/stage-2/y-tensioner-housing.stl). The hardware is also exactly the same as the right one (one M5x25 bolt and nut, one M3x25 screw and nut, and one 3mm pulley).

To secure it to the frame, just use one of the M4 T-nuts from the old tensioner. Assembly is the same as the right side.

{% endcapture %}
{% include docs-step.html
  heading="### Left Y Tensioner"
  image="/assets/images/docs/stages/stage-2/left-y-tensioner.png"
  content=ytensioner
%}


{% capture xtensioner %}
In addition to making belt tightening much easier and precise, this will also drop a bit more weight from the X gantry.

Assembly here is pretty straightforward. Remember when you saved the M5 screws from the wheel plates? Well, because those M5 threads were cut all the way through the extrusion, we can reuse that hole to secure our X tensioner from the top! It will be held from wobbling on side-to-side by the lower peg that slots right into your left Y rail block.

The rest of the parts (the slider, knob, and hardware) are the same as the other tensioners. You'll just need to print the main housing [here](https://raw.githubusercontent.com/endorphin3d/endorphin/main/STLs/stage-2/x-tensioner-housing.stl) then assemble it like the others.

{% endcapture %}
{% include docs-step.html
  heading="### X Tensioner"
  video="/assets/vids/docs/stages/stage-2/x-tensioner.mp4"
  content=xtensioner
%}

{% capture xtensionerplating %}
There's a flatter side near the back to make printing easier. The auto-orient feature of many slicers should pick the right side. If your overhang/cooling settings are dialed in you might not even need support!

{% endcapture %}
{% include docs-step.html
  heading="#### Plating"
  image="/assets/images/docs/stages/stage-2/x-tensioner-plating.png"
  content=xtensionerplating
%}
---

[← Back](/docs/stages/stage-1){: .btn .btn-outline .mr-4 .fs-5 } [Next →](/docs/stages/stage-3){: .btn .btn-outline .fs-5 }