---
title: "The Cartesian Hand: In-Hand Manipulation with All-Linear Fingers"
date: 2026-09-22
authors: ["B. Xia*", "B. Li*", "R. Shin", "Z. Yang", "J. Liu", "B. Chen"]
publication: "arXiv preprint arXiv:2609.25696"
year: 2026
preprint: true
status: "Preprint"
thumbnail: /publications/2026-cartesian-hand/thumb.gif
arxiv: https://arxiv.org/abs/2609.25696
pdf: https://arxiv.org/pdf/2609.25696
website: https://generalroboticslab.com/cartesian_handv1
research: true
home_tag: "Precision"
home_piece: "A 7-DoF hand that uses only linear joints. It opens caps, pipettes, and drives screws on 35 lab, factory, and household objects, and two of them do bimanual lab work on a humanoid."
abstract: "A 7-DoF end-effector that pairs two independently actuated parallel grippers with four translating fingertips, so one hand can both hold an object and move its parts relative to each other. Manipulation is built from simple linear motion primitives. Demonstrations include cap opening, pipetting, pumping, screwdriving, trigger actuation, and in-grasp reorientation across 35 objects, and the same procedures transfer from a fixed robot arm to a humanoid with two hands."
---

## Abstract

Robotic manipulation has increasingly pursued human-like dexterous hands with many articulated degrees of freedom, offering rich manipulation capabilities at the cost of mechanical and control complexity. At the other extreme, parallel grippers are simple and robust, but provide little ability to manipulate an object after grasping it. Operating articulated objects such as threaded containers, manufacturing tools, and laboratory instruments often requires a second gripper, an external fixture, or coordinated arm motion. We introduce the Cartesian Hand, a 7-DoF end-effector that rethinks dexterous manipulation by combining independent grasping and relative manipulation within a single end-effector using only linear motion. Two independently actuated parallel grippers hold different parts of an object, while four translating fingertips generate relative motion between the grasped parts. Its configuration-independent fingertip kinematics allow manipulation to be composed from simple linear motion primitives. The Cartesian Hand is particularly suited to objects structured around common mechanisms such as threads, pivots, linear guides, plungers, and triggers. We demonstrate cap opening and closing, pipetting, pumping, two-handle manipulation, screwdriving, trigger actuation, and in-grasp reorientation across 35 objects spanning laboratory, manufacturing, and household settings. The same manipulation procedures transfer from a fixed-base robot arm to a humanoid, where we demonstrate bimanual laboratory manipulation using two Cartesian Hands. These results show that versatile in-hand manipulation capability can emerge from a mechanically simple architecture when independent grasping and relative motion are designed directly into the end-effector.

## Overview

<figure>
  <img src="/publications/2026-cartesian-hand/fig1.jpg" alt="The Cartesian Hand and six of the objects it manipulates" style="width:100%;border-radius:4px">
  <figcaption>(a) Seven linear joints control gripper opening, gripper separation, and fingertip translation. (b) Examples of articulated objects from laboratory, manufacturing, and household settings: syringe, pliers, pipette, manual screwdriver, light bulb, and butane torch.</figcaption>
</figure>

## Links

- [Paper (arXiv)](https://arxiv.org/abs/2609.25696)
- [PDF](https://arxiv.org/pdf/2609.25696)
- [Project website](https://generalroboticslab.com/cartesian_handv1)

## Citation

```bibtex
@article{xia2026cartesian,
  title={The Cartesian Hand: In-Hand Manipulation with All-Linear Fingers},
  author={Xia, Boxi and Li, Bokuan and Shin, Ryan and Yang, Zijiang and Liu, Jiaxun and Chen, Boyuan},
  journal={arXiv preprint arXiv:2609.25696},
  year={2026}
}
```
