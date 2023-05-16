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
  alt="Endorphin stage 1"
  content=preface
%}

---

## Bill Of Materials

#### Bolts

| Part              | Type              | Quantity |
| :---------------- | :---------------- | :------- |
| M3X12 socket head | ISO 4762, DIN 912 | 4        |
| M3X25 socket head | ISO 4762, DIN 912 | 4        |
| M5X25 hex head    | ISO 4017, DIN 933 | 1        |

#### Hex Nuts

| Part           | Type               | Quantity |
| :------------- | :----------------- | :------- |
| M3-0.5 hex nut | DIN 934            | 3        |
| M5-0.8 hex nut | DIN 985, ISO 10511 | 1        |

#### Belt

| Part     | Size     | Quantity | Link                                                                                     |
| :------- | :------- | :------- | :--------------------------------------------------------------------------------------- |
| GT2 belt | 6mm wide | 1        | [Amazon](https://www.amazon.com/Upgrade-Non-Slip-Version-Printer-Printers/dp/B08R93QQ8Z) |

#### Pulleys

| Part                | Size                        | Quantity | Link                                                                                  |
| :------------------ | :-------------------------- | :------- | :------------------------------------------------------------------------------------ |
| GT2 toothless idler | 3mm bore, 20-tooth diameter | 5        | [Amazon](https://www.amazon.com/BIQU-Aluminum-Toothless-Timing-Printer/dp/B01H3F8LUU) |

---

{% capture printing %}
It should be easy to guess the print orientation for most of these parts. The only difficult one is the oddly-shaped front corner assembly. There's one particularly flat face on the part that has no fillets on the corners; this is the face that was designed to be on the print bed.

You should use **100% infill** for these parts and at least **4 perimeters/walls** (for screw hole durability). Parts printed with 0.2mm layer height look fantastic but 0.24mm is several hours faster.
{: .text-justify }
{% endcapture %}
{% include docs-step.html
  heading="## Printing"
  image="/assets/images/docs/stages/stage-1/plating.png"
  alt="Endorphin stage 1 plating"
  content=printing
%}

{% capture fca %}
1. Remove screws from front-right Y tensioner plate and set them aside for step 3
1. Remove the screw from the tensioner keeping the Y belt captured
1. Attach the front corner piece, reusing the M5 bolt and one of the M3 T-nut screws from the original plate on one side and the other M3 T-nut on the other corner of the aluminum extrusion
{% endcapture %}
{% include docs-step.html
  heading="## Front Corner Assembly"
  video="/assets/vids/docs/stage-1/assembly-front-corner.mp4"
  content=fca
%}

{% capture idlers %}
Next you'll install the right Y belt tensioner and the X belt's front idler. If you bought the 5 pack of smooth idlers linked in the BOM, you can use those both here and as the center idlers.

1. Hook the X belt onto a 20-tooth, 3mm bore idler and slide it into place
1. Insert an M3X25 screw through the top and secure it onto the underside with a hex nut
1. Insert the M5 hex nut into the hexagon slot on the inside of the Y belt tensioner and an M3 hex nut into the slot on the outer right side
1. Hook the Y belt on another 20-tooth idler and slide it into the tensioner housing
1. Place the tensioner housing inside the corner assembly and secure it into place with an M3X25 screw which will pass through housing and idler and thread into the hex nut on the other side. The tensioner housing should now slide forward and back to tension the belt.
1. Push the M5 bolt through the tensioner knob and thread it into the tensioner housing. Twist the knob until the right Y belt is as tight as the left.
{% endcapture %}
{% include docs-step.html
  heading="## Front Idlers"
  video="/assets/vids/docs/stage-1/assembly-driven-idlers.mp4"
  content=idlers
%}

{% capture x-stepper %}
1. Remove the screws on the back-right Y-axis pulley bracket and set aside
1. Install the new stepper mount by on top of the old bracket, putting the screws back in the same places they were
1. Remove the X stepper from the X gantry by removing the 4 screws on the top
1. Move the stepper to its new mount and secure it with four M3x12 screws
{% endcapture %}
{% include docs-step.html
  heading="## Move The X Stepper"
  video="/assets/vids/docs/stage-1/assembly-driving-mount.mp4"
  content=x-stepper
%}

### Swap Motors
{: .d-inline-block }

Optional
{: .label .label-blue .my-0 }

If you're using a direct drive extruder, you can make use of your old extruder stepper to drive the X belt. Because it's a stronger motor than the original X stepper, you'll be able to run the printer at higher speeds without skipping.

In fact, even if you *are* running the original extruder, you can still swap the extruder and X motors without issue. As long as your hotend is able to keep up with the filament feed rate, the original X stepper should have enough torque to be used as the extruder motor.

### Tune Stepper Current
{: .d-inline-block }

Optional
{: .label .label-blue .my-0 }

If you find that your X stepper motor is getting hot during long prints, you can turn your stepper current down a bit. Just follow [this guide](https://all3dp.com/2/vref-calculator-tmc2209-tmc2208-a4988) which should only take a few minutes to complete.

{% capture center-idlers %}
{% endcapture %}
{% include docs-step.html
  heading="## Center Idlers"
  video="/assets/vids/docs/stage-1/assembly-center-idlers.mp4"
  content=center-idlers
%}

---

[← Back](/docs/stages){: .btn .btn-outline .mr-4 .fs-5 } [Next →](/docs/stages/stage-2){: .btn .btn-outline .fs-5 }