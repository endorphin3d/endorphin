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

Deciding which face to print is somewhat of a tossup for these two pieces, as far as strength goes. Pictured is the print orientation used for testing and the test printer has been going strong for 6 months now with no issues.
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
1. Remove the two screws on the underside of the plate which attach it to the X gantry and save one of these screws for later
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
1. Using M3x8 screws and T-nuts, attach the MGN12 rail to the **inside** of the frame (this is where the alignment tool comes in handy)
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

---

[← Back](/docs/stages/stage-1){: .btn .btn-outline .mr-4 .fs-5 } [Next →](/docs/stages/stage-3){: .btn .btn-outline .fs-5 }