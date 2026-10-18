---
title: "Visible-Reachable Workspace for Perception-Aware Humanoid Design"
date: 2026-09-08
authors: ["B. Xia", "Z. Yang", "R. Shin", "B. Li", "E. W.-H. Lu", "J. Lee", "J. Liu", "B. Chen"]
publication: "arXiv preprint"
year: 2026
research: true
home_tag: "Perception for manipulation"
home_piece: "A 31-DoF humanoid whose two cameras move independently. It can see 97% of the space it can reach (38% with fixed cameras) and watch two separated targets while working on them."
preprint: true
featured: true
status: "Preprint"
thumbnail: /publications/2026-vrw-humanoid/thumb.gif
arxiv: https://arxiv.org/abs/2609.08905
pdf: https://arxiv.org/pdf/2609.08905
website: https://generalroboticslab.com/DukeHumanoidV2
code: https://github.com/generalroboticslab/duke_humanoid_v2
abstract: "We introduce the visible-reachable workspace (VRW), a design-stage measure that conditions visibility on feasible reaching configurations, and apply it to build Duke Humanoid V2, a 31-DoF humanoid with two independently actuated RGB-D cameras. Camera articulation raises visible-reachable coverage from 38% to 97%, and the dual-actuated design cuts two-target reach-and-grasp completion time by 17% and energy by 19% versus the same robot with fixed cameras."
---

## Abstract

Workspace analysis measures where a robot can place its end effector. For visually guided manipulation, reachability alone is insufficient: a kinematically reachable target may not be visible in the specific pose required to reach it. The robot must then redirect its sensing or move its body to acquire a view, turning a perception limitation into additional motion. Existing humanoids largely inherit this limitation when copying human form factors. We introduce the visible-reachable workspace (VRW), a design-stage measure that conditions visibility on feasible reaching configurations and extends it to concurrent visibility of spatially separated work regions. We apply VRW by building a 31-DoF humanoid with independently actuated RGB-D cameras. On the same robot, camera articulation increases visible-reachable coverage from 38% to 97%. With actuated camera layouts, a second camera raises pairwise coverage from 0.45 to 0.95, while a third changes it only to 0.97. In a controlled two-target reach-and-grasp benchmark, our dual-actuated design reduces mean completion time by 17% and mechanical energy by 19% relative to the same robot with its cameras fixed. Hardware experiments demonstrate simultaneous observation and manipulation of front/back and left/right target pairs without torso reorientation. The results suggest that reachability becomes a more informative design quantity for perception-driven humanoid manipulation when it is evaluated together with the sensing configurations that make the reachable space observable. We will open-source all software and the humanoid hardware design.

## Video

{{< youtube tKMAzhqL58o >}}

## Overview

Two moving targets carried by two people on opposite sides. Each camera module tracks one target and the arm on that side follows it, both at once.

<img src="/publications/2026-vrw-humanoid/hardware_tracking.webp" alt="Duke Humanoid V2 tracking two moving targets on hardware" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

<img src="/publications/2026-vrw-humanoid/teaser.png" alt="Duke Humanoid V2 in simulation and on hardware" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

## Visible-Reachable Workspace

A humanoid can usually reach far more space than it can see. VRW keeps only the reachable targets that can also be observed from a feasible reaching configuration. A pairwise extension, η₂, asks whether a layout can keep concurrent views of a manipulation target and a second, separated region.

Both configurations have the same arms and body and differ only in whether the camera joints are free. Magenta is visible-reachable, and blue is reachable but blind.

<img src="/publications/2026-vrw-humanoid/vrw_fixed_vs_actuated.webp" alt="Visible-reachable workspace, fixed versus actuated cameras" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

Visible-reachable workspace across humanoid platforms.

<img src="/publications/2026-vrw-humanoid/workspace.png" alt="Visible-reachable workspace across platforms" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

Actuating the cameras raises visible-reachable coverage from 38% to 97%, while a second and third camera module add under 3%. The second module matters for watching two places at once: pairwise coverage η₂ rises from 0.45 to 0.95 and stays nearly constant as the two work regions move apart.

## Two-Target Reach-and-Grasp Benchmark

Six simulated scenarios and 900 trials, with success-conditional means (lower is better). Act₂ (two actuated cameras) is the adopted configuration.

| | Time (s) | Search (s) | Approach (s) | Manipulation (s) | Energy (J) |
| --- | ---: | ---: | ---: | ---: | ---: |
| Unitree G1 | 27.5 | 3.8 | 3.8 | 19.9 | 494 |
| Fix₂ | 17.0 | 0.2 | 3.2 | 13.6 | 425 |
| **Act₂ (ours)** | **14.1** | **0.1** | **2.1** | **11.9** | **346** |
| Fix₁ | 20.5 | 3.3 | 3.3 | 13.9 | 595 |
| Act₁ | 15.5 | 0.6 | 2.7 | 12.2 | 385 |

<img src="/publications/2026-vrw-humanoid/two_target_left_right_far.webp" alt="Two targets left and right, benches far, under four camera configurations" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

## Real-World Deployment

Four hardware trials play together in each clip.

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:8px;margin:1em 0">
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Left and right, within reach</p>
    <img src="/publications/2026-vrw-humanoid/hardware_close_left_right.webp" alt="Left/right close, four hardware trials" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Front and behind</p>
    <img src="/publications/2026-vrw-humanoid/hardware_close_front_back_small.webp" alt="Front/back close, four hardware trials" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
</div>

## Hardware

<img src="/publications/2026-vrw-humanoid/hardware.png" alt="Duke Humanoid V2 hardware with actuated joints and modules labeled" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

| Specification | Value |
| --- | --- |
| DoF | 31: 27-DoF body + two 2-DoF camera gimbals, +1 per gripper |
| Mass / height | 36 kg / 1.2 m |
| Arm reach / leg length | 0.46 m / 0.39 m |
| Cameras | 2 × RGB-D, each on its own yaw-pitch gimbal |
| End effectors | Parallel grippers, 350 g each |
| Actuation | Quasi-direct-drive throughout |
| Control | 50 Hz learned whole-body policy, 200 Hz CAN motor loop |

## Interview

RealSense interviewed us about Duke Humanoid v2: [watch on YouTube](https://youtu.be/LFETWcjtMyM).

## Links

- [Project Website](https://generalroboticslab.com/DukeHumanoidV2)
- [Paper (arXiv)](https://arxiv.org/abs/2609.08905)
- [PDF](https://arxiv.org/pdf/2609.08905)
- [Code](https://github.com/generalroboticslab/duke_humanoid_v2)
- [Open-source hardware](https://generalroboticslab.github.io/Duke_Humanoid_V2_OpenSource/)

## Citation

```bibtex
@misc{xia2026visiblereachableworkspaceperception,
      title={Visible-Reachable Workspace for Perception-Aware Humanoid Design},
      author={Boxi Xia and Zijiang Yang and Ryan Shin and Bokuan Li and Eric Wun-Hao Lu and Jacob Lee and Jiaxun Liu and Boyuan Chen},
      year={2026},
      eprint={2609.08905},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2609.08905},
}
```
