---
layout: default
title: Stage 1
nav_order: 1
parent: Stages
permalink: docs/stages/stage-1
---

![Endorphin stage 1](/assets/images/docs/stages/stage-1/stage-1-render-lg.png)
{: .w-1_2 .float-right }

# Stage 1: Hybrid CoreXY
{: .no_toc }

> The goal of this stage is to drop the heaviest single part on the X carriage: **The stepper motor**. This stage alone will remove almost half a pound of moving weight but only takes a few hours to print and assemble.
{: .fs-5 .fw-300 .text-grey-dk-100 .text-justify }

## Table of contents
{: .no_toc .text-delta .mt-8 }

- TOC
{:toc}

---
{: .clear-both }

![Endorphin stage 1 plating](/assets/images/docs/stages/stage-1/plating.png)
{: .w-3_5 .h-80 .float-left }

## Printing

It should be easy to guess the print orientation for most of these parts. The only difficult one is the oddly-shaped front corner assembly. There's one particularly flat face on the part that has no fillets on the corners; this is the face that was designed to be on the print bed.
{: .text-justify }

You should use **100% infill** for these parts and at least **4 perimeters/walls** (for screw hole durability). Parts printed with 0.2mm layer height look fantastic but 0.24mm is several hours faster.
{: .text-justify }

## Front Corner Assembly
{: .clear-both }

#### Remove Original Y Tensioner Plate And Install New Assembly
{: .mb-4 }

<video muted autoplay controls loop class="w-7_12 float-right">
  <source src="/assets/vids/docs/assembly-front-corner.mp4" type="video/mp4">
</video>

1. Remove screws from front-right Y tensioner plate and set them aside for step 3
1. Remove the screw from the tensioner keeping the Y belt captured
1. Attach the new assembly to the frame, reusing the screws from the original plate

## Move The X Stepper
{: .clear-both }

### Swap Motors
{: .d-inline-block }

Optional
{: .label .label-blue }

If you're using a direct drive extruder, you can make use of your old extruder stepper to drive the X belt. Because it's a stronger motor than the original X stepper, you'll be able to run the printer at higher speeds without skipping.

In fact, even if you *are* running the original extruder, you can still swap the extruder and X motors without issue. As long as your hotend is able to keep up with the filament feed rate, your extruder stepper doesn't need an enormous amount of torque.

## Tune Stepper Current