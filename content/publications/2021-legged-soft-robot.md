---
title: "A legged soft robot platform for dynamic locomotion"
date: 2021-05-01
authors: ["B. Xia", "J. Fu", "H. Zhu", "Z. Song", "Y. Jiang", "H. Lipson"]
publication: "2021 IEEE International Conference on Robotics and Automation (ICRA)"
pages: "11812–11819"
year: 2021
conference: true
publication_short: "ICRA 2021"
doi: 10.1109/ICRA48506.2021.9561018
pdf: /publications/2021-legged-soft-robot/2021-legged-soft-robot.pdf
thumbnail: /publications/2021-legged-soft-robot/flexipod_at_columbia.jpg
code: https://github.com/boxiXia/FlexipodHardware
---

# A legged soft robot platform for dynamic locomotion

**Authors:** **B. Xia¹**, J. Fu¹, H. Zhu¹, Z. Song¹, Y. Jiang¹, H. Lipson¹

¹Columbia University, Creative Machines Lab

**Publication:** *2021 IEEE International Conference on Robotics and Automation (ICRA)*, pp. 11812–11819 (2021)

**Presentation:** Poster

**DOI:** [10.1109/ICRA48506.2021.9561018](https://doi.org/10.1109/ICRA48506.2021.9561018)

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:8px;margin:1.5em 0">
  <img src="/publications/2021-legged-soft-robot/flexipod_at_columbia.jpg" alt="Flexipod at Columbia University" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2021-legged-soft-robot/morningside_park_unstructured.jpg" alt="Flexipod on unstructured terrain at Morningside Park" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2021-legged-soft-robot/bounding_mat.jpg" alt="Flexipod bounding on mat" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2021-legged-soft-robot/columbia_brick.jpg" alt="Flexipod on brick surface at Columbia" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2021-legged-soft-robot/morningside_park_grass.jpg" alt="Flexipod on grass" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2021-legged-soft-robot/morningside_park_sand.jpg" alt="Flexipod on sand" style="width:100%;height:auto;display:block;border-radius:4px">
</div>

## Abstract

This paper presents an open-source untethered quadrupedal soft robot platform for dynamic locomotion (e.g., high-speed running and backflipping). The robot is mostly soft (80 vol.%) while driven by four geared servo motors. The robot's soft body and soft legs were 3D printed with gyroid infill using a flexible material, enabling it to conform to the environment and passively stabilize during locomotion in multi-terrain environments. In addition, we simulated the robot in a real-time soft body simulation. With tuned gaits in simulation, the real robot can locomote at a speed of 0.9 m/s (2.5 body length/second), substantially faster than most untethered legged soft robots published to date. We hope this platform, along with its verified simulator, can catalyze agile soft robots' development.

## Paper Video

{{< youtube 3h0RwY_tpGc >}}

## Material

The flexible material used for printing the soft body and legs is a flexible TPU (Cheetah flexible filament, Ninjatek). Although the filament has a shore hardness of 95A, it is possible to achieve lower hardness by varying the infill density and flow rate.

<figure>
  <img src="/publications/2021-legged-soft-robot/material_flow_infill_hardness.jpg" alt="Shore hardness vs flow rate and infill density" style="width:100%;border-radius:4px">
  <figcaption>(a) Shore hardness vs. flow rate and infill density; (b–c) 3D printed cross-sections of (b) gyroid 20% infill density and 90% flow rate, and (c) 16% infill density and 80% flow rate.</figcaption>
</figure>

## Body Design

The body is printed with flexible material. 96 vol.% of the 3D printed parts are soft, making the robot 80 vol.% soft overall.

<figure>
  <img src="/publications/2021-legged-soft-robot/body_open.jpg" alt="Soft robot structure" style="width:100%;border-radius:4px">
  <figcaption>Structure of the soft robot: (1) Soft main body; (2) Camera; (3) Electronic components; (4) Li-Po battery; (5) Bearing; (6) DJI M3508 brushless DC motor enclosed in a motor shell; (7) Soft leg.</figcaption>
</figure>

## Soft Leg

The leg's hollowed structure makes it flexible and impact resistant. To demonstrate its damping effect, we dropped the Flexipod from as high as 2.0 m. At impact, the soft legs compressed and the body bent inward to absorb the impact, allowing the robot to recover on its own.

<figure>
  <img src="/publications/2021-legged-soft-robot/leg.jpg" alt="Flexipod soft leg design and drop test" style="width:60%;display:block;margin:0 auto;border-radius:4px">
  <figcaption>Flexipod soft leg and demonstration: (a) Soft leg, leg coupler and bearing; (b) 3D model of the leg assembly showing its internal structure; (c) chronophotograph of the Flexipod dropped from 2.0 m.</figcaption>
</figure>

## Simulation

We developed a soft robot simulation environment based on [Titan](https://github.com/jacobaustin123/Titan) — a CUDA-accelerated massively parallel asynchronous spring-mass simulation library. We extended Titan with a rotational kernel for contact-coupling of soft bodies. The Flexipod simulation achieved 10⁹ spring evaluations per second on a consumer Nvidia 2080Ti GPU.

{{< youtube 52yaNeKdhIc >}}

## Locomotion Patterns

<figure>
  <img src="/publications/2021-legged-soft-robot/gait.jpg" alt="Flexipod locomotion patterns" style="width:100%;border-radius:4px">
  <figcaption>(a) Bounding gait; (b) pace gait; (c) turning; (d) backflip.</figcaption>
</figure>

### Backflips

{{< youtube JLf9fDQOb48 >}}

### Locomotion in the Wild

{{< youtube dFAsGUMLO9U >}}

## Links

- [Download PDF](/publications/2021-legged-soft-robot/2021-legged-soft-robot.pdf)
- [Full text (IEEE Xplore)](https://ieeexplore.ieee.org/document/9561018)
- [Hardware (GitHub)](https://github.com/boxiXia/FlexipodHardware)
- [Simulation (GitHub)](https://github.com/boxiXia/FlexipodFast)

## People

[Boxi Xia](https://github.com/boxiXia), [Jiaming Fu](https://uwf.edu/hmcse/departments/mechanical-engineering/faculty/dr-jiaming-fu.html), [Hongbo Zhu](https://github.com/DonovanZhu), [Zhicheng Song](https://github.com/ZhichengSong6), [Yibo Jiang](https://github.com/YiboJ12), [Hod Lipson](https://www.hodlipson.com/)

[Creative Machines Lab](https://www.creativemachineslab.com/) at Columbia University

## Paper

<object data="/publications/2021-legged-soft-robot/2021-legged-soft-robot.pdf" type="application/pdf" width="100%" height="800px" style="border:none;"><p>PDF cannot be displayed. <a href="/publications/2021-legged-soft-robot/2021-legged-soft-robot.pdf">Download PDF</a></p></object>

## Citation

```bibtex
@inproceedings{xia2021legged,
  title={A legged soft robot platform for dynamic locomotion},
  author={Xia, B. and Fu, J. and Zhu, H. and Song, Z. and Jiang, Y. and Lipson, H.},
  booktitle={2021 IEEE International Conference on Robotics and Automation (ICRA)},
  pages={11812--11819},
  year={2021},
  organization={IEEE}
}
```
