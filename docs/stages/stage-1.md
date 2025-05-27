---
layout: default
title: Stage 1
nav_order: 1
parent: Stages
permalink: docs/stages/stage-1
---

{% capture preface %}
> The goal of this stage is to drop the heaviest single part on the X carriage: **The stepper motor**. This stage alone will remove almost half a pound of moving weight but only takes a few hours to print and assemble.
{: .fs-5 .fw-300 .text-grey-dk-100 .text-justify }
{% endcapture %}
{% include docs-preface.html
  title="# Stage 1: Hybrid CoreXY"
  image="/assets/images/docs/stages/stage-1/stage-1-render-lg.png"
  content=preface
%}

---

## Bill Of Materials

#### Bolts

| Part              | Type              | Quantity |
| :---------------- | :---------------- | :------- |
| M3x12 socket head | ISO 4762, DIN 912 | 4        |
| M3x25 socket head | ISO 4762, DIN 912 | 4        |
| M5X25 hex head    | ISO 4017, DIN 933 | 1        |

#### Washers

| Part | Type    | Quantity |
| :--- | :------ | :------- |
| M3   | DIN 125 | 6        |

#### Hex Nuts

| Part           | Type               | Quantity |
| :------------- | :----------------- | :------- |
| M3-0.5 hex nut | DIN 934            | 3        |
| M5-0.8 hex nut | DIN 985, ISO 10511 | 1        |

#### Belt

| Part     | Size              | Quantity | Link                                                                                     |
| :------- | :---------------- | :------- | :--------------------------------------------------------------------------------------- |
| GT2 belt | 6mm wide, 5m long | 1        | [Amazon](https://www.amazon.com/Upgrade-Non-Slip-Version-Printer-Printers/dp/B08R93QQ8Z) |

#### Pulleys

| Part                | Size                        | Quantity | Link                                                                            |
| :------------------ | :-------------------------- | :------- | :------------------------------------------------------------------------------ |
| GT2 toothless idler | 3mm bore, 20-tooth diameter | 5        | [Amazon](https://www.amazon.com/BZ-3D-Aluminum-Printer-Toothless/dp/B08726CGYJ) |

---

{% capture printing %}
**STL files for this stage are** [here](https://github.com/endorphin3d/endorphin/tree/main/STLs/stage-1)

It should be easy to guess the print orientation for most of these parts. The only difficult one is the oddly-shaped front corner assembly. There's one particularly flat face on the part that has no fillets on the corners; this is the face that was designed to be on the print bed.

You should use **100% infill** for these parts and at least **4 perimeters/walls** (for screw hole durability). Parts printed with 0.2mm layer height look fantastic but 0.24mm is several hours faster.
{: .text-justify }
{% endcapture %}
{% include docs-step.html
  heading="## Printing"
  image="/assets/images/docs/stages/stage-1/plating.png"
  content=printing
%}

{% capture fca %}
1. Remove screws from front-right Y tensioner plate and set them aside for step 3
1. Remove the screw from the tensioner keeping the Y belt captured
1. Attach the front corner piece, reusing the M5 bolt and one of the M4 T-nut screws from the original plate on one side and the other M4 T-nut on the other corner of the aluminum extrusion
{% endcapture %}
{% include docs-step.html
  heading="## Front Corner Assembly"
  video="/assets/vids/docs/stages/stage-1/assembly-front-corner.mp4"
  content=fca
%}

{% capture pulleys %}
Next you'll install the right Y belt tensioner and the X belt's front pulley. If you bought the 5 pack of smooth pulleys linked in the BOM, you can use those both here and as the center pulleys.

1. Hook the X belt onto a 20-tooth, 3mm bore pulley and slide it into place
1. Add a washer to the top and bottom of the pulley
1. Insert an M3x25 screw through the top and secure it onto the underside with a hex nut
1. Insert the M5 hex nut into the hexagon slot on the inside of the Y belt tensioner and an M3 hex nut into the slot on the outer right side
1. Hook the Y belt on another 20-tooth pulley and slide it into the tensioner housing
1. (Optional) Add a washer on both sides of the pulley. This isn't as critical as the other pulleys which are pulled into plastic due to gravity
1. Place the tensioner housing inside the corner assembly and secure it into place with an M3x25 screw which will pass through housing and pulley and thread into the hex nut on the other side. The tensioner housing should now slide forward and back to tension the belt.
1. Push the M5 bolt through the tensioner knob and thread it into the tensioner housing. Twist the knob until the right Y belt is as tight as the left.
{% endcapture %}
{% include docs-step.html
  heading="## Front Pulleys"
  video="/assets/vids/docs/stages/stage-1/assembly-driven-pulleys.mp4"
  content=pulleys
%}

{% capture x-stepper %}
1. Remove the screws on the back-right Y-axis pulley bracket and set aside
1. Install the new stepper mount by on top of the old bracket, putting the screws back in the same places they were
1. Remove the X stepper from the X gantry by removing the 4 screws on the top
1. Move the stepper to its new mount and secure it with four M3x12 screws
{% endcapture %}
{% include docs-step.html
  heading="## Move The X Stepper"
  video="/assets/vids/docs/stages/stage-1/assembly-driving-mount.mp4"
  content=x-stepper
%}

{% capture center-idlers %}
These two center idlers are the reason we're using ones with a 3mm bore throughout the project rather than the more common 5mm bore. Because we're making use of two of the stepper mounting holes on the original X stepper plate to hold the axles for the idlers. These holes are only large enough to use M3 screws as axles, hence the 3mm bore pulleys.

1. Remove the old X belt if you haven't already
1. Place the bottom center idler block on top of the carriage (the bottom plate is the one without the hexagon holes)
1. Sandwich two pulleys between washers and set them on top of the idler block
1. Insert two M3 hex nuts into the top idler block and place on top of the pulleys
1. Drive two M3x25 screws from the underside, passing through the holes original steel plate and then through our stack of new parts, finally threading into the hex nuts in the top center idler block
{% endcapture %}
{% include docs-step.html
  heading="## Center Idlers"
  video="/assets/vids/docs/stages/stage-1/assembly-center-idlers.mp4"
  content=center-idlers
%}

### A Note On Washers

These little M3 washers can be tricky to install, and you may be tempted to skip them altogether. A good rule of thumb is anywhere that gravity is at play on a pulley, you'll need a washer so it doesn't rub. In short: Washers are going to be *highly* recommended on the X axis pulleys, but not so critical on the Y tensioners.

## Optional Steps

### Swap Motors
{: .d-inline-block }

Highly Recommended
{: .label .label-red .my-0 }

In the original Ender 5, the X stepper only needed to be strong enough to move the printhead. Now it will be sharing the weight of the entire carriage with the Y stepper (which you'll notice is a bigger motor). This is why it's highly recommended to swap the extruder stepper and the X stepper. This will allow you to reach higher speeds without skipping.

### Tune Stepper Current
{: .d-inline-block }

If you find that your X stepper motor is getting hot during long prints, you can turn your stepper current down a bit. Just follow [this guide](https://all3dp.com/2/vref-calculator-tmc2209-tmc2208-a4988) which should only take a few minutes to complete.

### Stealthchop and Torque
{: .d-inline-block }

Klipper Only
{: .label .label-blue .my-0 }

Stealthchop is a feature in many modern boards which quiets the stepper motor at the expense of slight inaccuracies and reduced torque. For maximum speeds, you would want to **disable** Stealthchop. Unfortunately the "silent" boards that come in the Ender 5 require some soldering to disable Stealthchop (look up "Creality 4.2.2 and 4.2.7 UART mod").

That said, if you have a more modern board, you can disable Stealthchop for maximum torque while increasing your micro-steps to achive a very similar level of quiet from your steppers. Here's what you would add to your printer.cfg (change "tmc2209" to your model's stepper driver):

```yaml
[stepper_x]
...
microsteps: 128
rotation_distance: 40

[tmc2209 stepper_x]
...
run_current: 0.620
interpolate: False

[stepper_y]
...
microsteps: 128
rotation_distance: 40

[tmc2209 stepper_y]
...
run_current: 0.650
interpolate: False
```

## Troubleshooting

### Height adjustments

Once you've installed and tightened your hybrid X belt you might notice that it's not running perfectly parallel all the way along its path, or you might find that it's slightly too high or low and it's rubbing against the X rail after it passes through the center idlers. If this happens, there's a number of adjustments you can make, depending on what the issue is.

1. Raise/lower the pulley on the X motor (many but not all Ender 5 models have an adjustable grub screw on the pulley)
1. Raise the center idlers with another washer
1. Raise the front corner idler with another washer

### Quacking Noise

Sometimes during printing, mainly on faster travel moves, you might hear a sound that's reminiscent of an oversized goose honking. While it may seem like a mechanical issue (something rubbing, needing oil, etc.) it actually goes away completely when disabling StealthChop (see the StealthChop section above).

---

[← Back](/docs/stages){: .btn .btn-outline .mr-4 .fs-5 } [Next →](/docs/stages/stage-2){: .btn .btn-outline .fs-5 }
