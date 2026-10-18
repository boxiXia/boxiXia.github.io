---
title: "Dynamic Symmetry for Orientation-Independent Planetary Mobility"
date: 2026-09-28
authors: ["B. Xia*", "J. Liu*", "B. Chen"]
publication: "Space Robotics Workshop at IEEE/RSJ IROS 2026"
publication_short: "IROS 2026 Space Robotics Workshop"
year: 2026
research: true
home_tag: "Planetary mobility"
home_piece: "Applies dynamic symmetry to planetary surfaces: zero-shot trajectory tracking on simulated Mars and Moon terrain under reduced gravity."
workshop: true
award: "Best Paper Award"
presentation: "Oral"
thumbnail: /publications/2026-space-workshop/thumb.gif
pdf: /publications/2026-space-workshop/2026-space-workshop.pdf
website: https://space-robots.org/events/iros2026/
website_label: "Workshop Website"
abstract: "Planetary ground robots can overturn on crater slopes, uneven terrain, and obstacles. Argus, a family of spherical robots with radially distributed actuators, moves in any body orientation. Across 1,536 simulated morphologies, higher dynamic isotropy was associated with lower tracking error, higher task success, and lower cost of transport, including zero-shot tracking on simulated Mars and Moon terrain under reduced gravity. The physical 20-leg Argus climbed between parallel walls under counterweight-emulated lunar gravity and kept moving with disabled actuators."
---

Oral presentation at the Space Robotics Workshop, IEEE/RSJ IROS 2026, Pittsburgh, PA, where it received the workshop's Best Paper Award. The paper applies dynamic symmetry from the [Argus *Science Robotics* article](/publications/2026-argus/) to planetary surface mobility.

## Abstract

Planetary ground robots can overturn while traversing crater slopes, uneven terrain, and obstacles. Most ground robots are designed around an upright body configuration and a forward-facing sensor view, making locomotion and perception sensitive to body orientation. Hopping and tumbling robots can tolerate large attitude changes, while other systems use dedicated mechanisms to recover a preferred orientation, but neither approach provides continuous locomotion across arbitrary body orientations. We developed Argus, a family of spherical robots with radially distributed actuators that enable locomotion across body orientations. We describe this property as dynamic symmetry and quantify it with dynamic isotropy, a measure of how uniformly a robot can accelerate its center of mass across directions. Across 1536 simulated morphologies, higher dynamic isotropy was associated with lower trajectory-tracking error, higher task success, and lower cost of transport. We further evaluated Argus under planetary conditions, demonstrating zero-shot trajectory tracking on simulated Mars and Moon terrains under reduced gravity. A physical 20-leg Argus with near-extreme dynamic isotropy climbed a parallel-wall under counterweight-emulated lunar gravity, continued locomotion with disabled actuators, and transferred zero-shot to cluttered and deformable terrain. Argus's distributed sensing further removes the need for a preferred viewing direction, supporting target tracking and perception-guided pushing.

## Simulated Mars and Moon locomotion

Argus with 12, 20, and 32 DoF (left to right) following a figure-eight trajectory on simulated Mars (top row) and Moon (bottom row) terrain under each body's gravity. These videos correspond to Fig. 1f and 1g in the paper.

<figure>
  <video src="/publications/2026-space-workshop/grid_wide.mp4" autoplay muted loop playsinline controls preload="auto" style="width:100%;border-radius:4px"></video>
  <figcaption>Fixed top-down view. Pink is the commanded path and cyan is the robot's actual trajectory (Fig. 1f).</figcaption>
</figure>

<figure>
  <video src="/publications/2026-space-workshop/grid_chase.mp4" autoplay muted loop playsinline controls preload="auto" style="width:100%;border-radius:4px"></video>
  <figcaption>Camera following each robot (Fig. 1g).</figcaption>
</figure>

## Paper

<object data="/publications/2026-space-workshop/2026-space-workshop.pdf" type="application/pdf" width="100%" height="800px" style="border:none;"><p>PDF cannot be displayed. <a href="/publications/2026-space-workshop/2026-space-workshop.pdf">Download PDF</a></p></object>

## Links

- [Download PDF](/publications/2026-space-workshop/2026-space-workshop.pdf)
- [Space Robotics Workshop, IROS 2026](https://space-robots.org/events/iros2026/)
- [Argus journal article (Science Robotics)](/publications/2026-argus/)

## Citation

```bibtex
@inproceedings{xia2026dynamic,
  title={Dynamic Symmetry for Orientation-Independent Planetary Mobility},
  author={Xia, Boxi and Liu, Jiaxun and Chen, Boyuan},
  booktitle={Space Robotics Workshop at the IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  address={Pittsburgh, PA},
  year={2026}
}
```
