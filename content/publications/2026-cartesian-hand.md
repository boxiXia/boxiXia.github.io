---
title: "The Cartesian Hand: In-Hand Manipulation with All-Linear Fingers"
date: 2026-09-22
authors: ["B. Xia*", "B. Li*", "R. Shin", "Z. Yang", "J. Liu", "B. Chen"]
publication: "arXiv preprint"
year: 2026
research: true
home_tag: "Precision"
home_piece: "A 7-DoF hand that uses only linear joints. It opens caps, pipettes, and drives screws on 35 lab, factory, and household objects, and two of them do bimanual lab work on a humanoid."
preprint: true
featured: true
status: "Preprint"
thumbnail: /publications/2026-cartesian-hand/thumb.gif
arxiv: https://arxiv.org/abs/2609.25696
pdf: https://arxiv.org/pdf/2609.25696
website: https://generalroboticslab.com/cartesian_handv1
code: https://github.com/generalroboticslab/Cartesian_Hand
abstract: "We introduce the Cartesian Hand, a 7-DoF end-effector that combines independent grasping and relative manipulation using only linear motion. Two parallel grippers hold different parts of an object while four translating fingertips move them relative to each other, enabling cap opening, pipetting, pumping, screwdriving, trigger actuation, and in-grasp reorientation across 35 objects, on both a robot arm and a humanoid."
---

## Abstract

Robotic manipulation has increasingly pursued human-like dexterous hands with many articulated degrees of freedom, offering rich manipulation capabilities at the cost of mechanical and control complexity. At the other extreme, parallel grippers are simple and robust, but provide little ability to manipulate an object after grasping it. Operating articulated objects such as threaded containers, manufacturing tools, and laboratory instruments often requires a second gripper, an external fixture, or coordinated arm motion.

We introduce the Cartesian Hand, a 7-DoF end-effector that rethinks dexterous manipulation by combining independent grasping and relative manipulation within a single end-effector using only linear motion. Two independently actuated parallel grippers hold different parts of an object, while four translating fingertips generate relative motion between the grasped parts. Its configuration-independent fingertip kinematics allow manipulation to be composed from simple linear motion primitives. The Cartesian Hand is particularly suited to objects structured around common mechanisms such as threads, pivots, linear guides, plungers, and triggers.

We demonstrate cap opening and closing, pipetting, pumping, two-handle manipulation, screwdriving, trigger actuation, and in-grasp reorientation across 35 objects spanning laboratory, manufacturing, and household settings. The same manipulation procedures transfer from a fixed-base robot arm to a humanoid, where we demonstrate bimanual laboratory manipulation using two Cartesian Hands. These results show that versatile in-hand manipulation capability can emerge from a mechanically simple architecture when independent grasping and relative motion are designed directly into the end-effector.

## Video

{{< youtube ktNcPPTPsQE >}}

## Overview

One continuous run: spray bottle, pipette, then centrifuge-tube cap. Closing a jaw pulls the trigger, the separation joint presses the plunger, and fingertip slides twist the cap.

<video src="/publications/2026-cartesian-hand/seq-three-objects.mp4" poster="/publications/2026-cartesian-hand/seq-three-objects.jpg" autoplay muted loop playsinline style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px"></video>

| Specification | Value |
| --- | --- |
| Fingertip travel | 65 mm |
| Gripper and separation travel | 52 mm each |
| Joint speed | ≈ 60 mm/s |
| Static hold, one gripper | 2 kg |
| Mass | 850 g |
| Size | ≈ 166 × 100 × 76 mm |
| Structure | 3D-printed PLA or nylon |
| Cost | ≈ $500 |

## Kinematics

All seven joints are prismatic, so each joint moves its fingertips along a fixed axis, the same way in any configuration and with no singular poses. Each fingertip point is a fixed linear function of the joints, so the Jacobian is a constant matrix of full rank.

<img src="/publications/2026-cartesian-hand/hand-axes-4x3.jpg" alt="Linear axes: two stacked grippers, four sliding fingertips, and the gap between the grippers" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

<video src="/publications/2026-cartesian-hand/mechanism-joints.mp4" poster="/publications/2026-cartesian-hand/mechanism-joints.jpg" autoplay muted loop playsinline style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px"></video>

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:8px;margin:1em 0">
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Design: four actuated fingertips, P1–P4</p>
    <img src="/publications/2026-cartesian-hand/design-cad.jpg" alt="Cartesian Hand CAD design" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Joint frames: seven prismatic joints</p>
    <img src="/publications/2026-cartesian-hand/design-kinematics.png" alt="Cartesian Hand joint frames" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
</div>

Workspace: each fingertip reaches an axis-aligned box (base gripper orange, auxiliary gripper blue).

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:8px;margin:1em 0">
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Minimum configuration</p>
    <img src="/publications/2026-cartesian-hand/workspace-min.jpg" alt="Workspace at minimum configuration" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Maximum configuration</p>
    <img src="/publications/2026-cartesian-hand/workspace-max.jpg" alt="Workspace at maximum configuration" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
</div>

## Rubik's Cube Manipulation

Within one grasp, the hand alternates between holding the cube, turning a layer and reorienting it.

<video src="/publications/2026-cartesian-hand/demo-rubik.mp4" poster="/publications/2026-cartesian-hand/demo-rubik.jpg" autoplay muted loop playsinline style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px"></video>

## On a Humanoid

Two Cartesian Hands on Duke Humanoid v2: one hand opens a centrifuge tube while the other pipettes into it. The arms position the objects, and the hands do each operation.

<video src="/publications/2026-cartesian-hand/humanoid-bimanual-square.mp4" poster="/publications/2026-cartesian-hand/humanoid-bimanual-square.jpg" autoplay muted loop playsinline style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px"></video>

## Links

- [Project Website](https://generalroboticslab.com/cartesian_handv1)
- [Paper (arXiv)](https://arxiv.org/abs/2609.25696)
- [PDF](https://arxiv.org/pdf/2609.25696)
- [Code](https://github.com/generalroboticslab/Cartesian_Hand)
- [CAD and simulation model](https://github.com/generalroboticslab/Cartesian_Hand/tree/main/assets/cartesian_hand)

## Citation

```bibtex
@misc{xia2026cartesianhand,
      title={The Cartesian Hand: In-Hand Manipulation with All-Linear Fingers},
      author={Boxi Xia and Bokuan Li and Ryan Shin and Zijiang Yang and Jiaxun Liu and Boyuan Chen},
      year={2026},
      eprint={2609.25696},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2609.25696},
}
```
