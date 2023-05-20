---
layout: default
title: Stage 3
nav_order: 3
parent: Stages
permalink: docs/stages/stage-3
---

{% capture preface %}
> The purpose of this stage is to add a linear rail on the X axis. We'll basically be trading the weight from the original steel printhead carriage and its wheels for an MGN9 rail of similar weight. Thus, the benefits of this stage aren't as much weight removal as the ability to use a modern printhead such as the Ratrig EVA or the Vz Printhead, plus complete liberation from those frustrating v-slot wheels.
{: .fs-5 .fw-300 .text-grey-dk-100 .text-justify }
{% endcapture %}
{% include docs-preface.html
  title="# Stage 3: Linear X Rail"
  image="/assets/images/docs/stages/stage-3/stage-3-render-lg.png"
  content=preface
%}

---

## Bill Of Materials

#### Linear Rails

| Size         | Length | Quantity | Link                                                   |
| :----------- | :----- | :------- | :----------------------------------------------------- |
| MGN9H Rail   | 400mm  | 1        | [Amazon](https://www.amazon.com/gp/product/B09XQ7YWPT) |

#### Bolts

| Part             | Type              | Quantity | Link                                                   |
| :--------------- | :---------------- | :------- | :----------------------------------------------------- |
| M3x8 socket head | ISO 4762, DIN 912 | 8        | [Amazon](https://www.amazon.com/gp/product/B08R3GJGWT) |

#### T-Nuts

| Size           | Quantity | Link                                                   |
| :------------- | :------- | :----------------------------------------------------- |
| M3 2020 T-nuts | 8        | [Amazon](https://www.amazon.com/gp/product/B08NZMD2BJ) |

---

## Vz Printhead

**Usable Print Area:** 220 x 200 (20mm reduction on Y)

### Belt Clips

Either of the following belt clips provided with the printhead will work fine so pick whichever one you prefer. The original Vz printhead has been modified so that the posts sit at the right height for the Endorphin belts. Just remember that you only need to print off clips for 2 belt ends rather than the 4 needed in a CoreXY which means you can choose whether you want to attach the belt ends on the front or rear posts. The other two will be unused.
{: .mb-8 }

{% capture belts1 %}
This clip is incredibly simple to print and the gripping mechanism is equally simple: By circling the belt around the standoffs, teeth inward, the belt grips itself by interlacing its own teeth like a zipper. This is probably the best choice in terms of printability and simplicity.
{% endcapture %}
{% include docs-step.html
  heading="#### Belt Clip Style 1"
  image="/assets/images/docs/stages/stage-3/belt-clip-1.png"
  content=belts1
%}

{% capture belts2 %}
This is a two-part clip that has more intricate details to print, so make sure to use a small enough nozzle and/or thin layers. While also a clever design, it does look like the wings on the outer clip housing run the risk of spreading under enough tension and allowing the belt to slip.
{% endcapture %}
{% include docs-step.html
  heading="#### Belt Clip Style 2"
  image="/assets/images/docs/stages/stage-3/belt-clip-2.png"
  content=belts2
%}

## EVA

**Usable Print Area:** 220 x 190 (30mm reduction on Y)

[EVA CoreXY](https://main.eva-3d.page/heat_insert/core/corexy)

{% capture evabelts %}
{% endcapture %}
{% include docs-step.html
  heading="### EVA Belt"
  video="/assets/vids/docs/stages/stage-3/assembly-endorphin-belts.mp4"
  content=evabelts
%}

---

[← Back](/docs/stages/stage-2){: .btn .btn-outline .mr-4 .fs-5 }