---
title: "Visible-Reachable Workspace for Perception-Aware Humanoid Design"
date: 2026-09-08
authors: ["B. Xia", "Z. Yang", "R. Shin", "B. Li", "E.W.-H. Lu", "J. Lee", "J. Liu", "B. Chen"]
publication: "arXiv preprint arXiv:2609.08905"
year: 2026
preprint: true
status: "Preprint"
thumbnail: /publications/2026-duke-humanoid-v2/thumb.gif
arxiv: https://arxiv.org/abs/2609.08905
pdf: https://arxiv.org/pdf/2609.08905
website: https://generalroboticslab.com/DukeHumanoidv2
research: true
home_tag: "Perception for manipulation"
home_piece: "A 31-DoF humanoid whose two cameras move independently. It can see 97% of the space it can reach (38% with fixed cameras) and watch two separated targets while working on them."
abstract: "A robot can often reach a target it cannot see from the pose it needs to reach it. The visible-reachable workspace (VRW) measures where a robot can both reach and see, and we used it to design Duke Humanoid v2, a 31-DoF humanoid with two independently actuated RGB-D cameras. Camera articulation raises visible-reachable coverage from 38% to 97%, and in a two-target reach-and-grasp benchmark it cuts completion time by 17% and mechanical energy by 19% compared with fixed cameras."
---

## Abstract

Workspace analysis measures where a robot can place its end effector. For visually guided manipulation, reachability alone is insufficient: a kinematically reachable target may not be visible in the specific pose required to reach it. The robot must then redirect its sensing or move its body to acquire a view, turning a perception limitation into additional motion. Existing humanoids largely inherit this limitation when copying human form factors. We introduce the visible-reachable workspace (VRW), a design-stage measure that conditions visibility on feasible reaching configurations and extends it to concurrent visibility of spatially separated work regions. We apply VRW by building a 31-DoF humanoid with independently actuated RGB-D cameras. On the same robot, camera articulation increases visible-reachable coverage from 38% to 97%. With actuated camera layouts, a second camera raises pairwise coverage from 0.45 to 0.95, while a third changes it only to 0.97. In a controlled two-target reach-and-grasp benchmark, our dual-actuated design reduces mean completion time by 17% and mechanical energy by 19% relative to the same robot with its cameras fixed. Hardware experiments demonstrate simultaneous observation and manipulation of front/back and left/right target pairs without torso reorientation. The results suggest that reachability becomes a more informative design quantity for perception-driven humanoid manipulation when it is evaluated together with the sensing configurations that make the reachable space observable.

## Overview

<figure>
  <img src="/publications/2026-duke-humanoid-v2/fig1.jpg" alt="Duke Humanoid v2 and its visible-reachable workspace" style="width:100%;border-radius:4px">
  <figcaption>(a) Duke Humanoid v2 carries two independently actuated yaw-pitch RGB-D cameras. (b) Visible-reachable workspace with fixed versus actuated cameras. (c, d) The two cameras watch separated targets during left/right and front/back manipulation.</figcaption>
</figure>

## Interview

RealSense interviewed us about Duke Humanoid v2: [watch on YouTube](https://youtu.be/LFETWcjtMyM).

## Links

- [Paper (arXiv)](https://arxiv.org/abs/2609.08905)
- [PDF](https://arxiv.org/pdf/2609.08905)
- [Project website](https://generalroboticslab.com/DukeHumanoidv2)

## Citation

```bibtex
@article{xia2026visible,
  title={Visible-Reachable Workspace for Perception-Aware Humanoid Design},
  author={Xia, Boxi and Yang, Zijiang and Shin, Ryan and Li, Bokuan and Lu, Eric Wun-Hao and Lee, Jacob and Liu, Jiaxun and Chen, Boyuan},
  journal={arXiv preprint arXiv:2609.08905},
  year={2026}
}
```
