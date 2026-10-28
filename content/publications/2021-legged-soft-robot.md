---
title: "A legged soft robot platform for dynamic locomotion"
date: 2021-05-01
authors: ["B. Xia", "J. Fu", "H. Zhu", "Z. Song", "Y. Jiang", "H. Lipson"]
publication: "2021 IEEE International Conference on Robotics and Automation (ICRA)"
pages: "11812–11819"
year: 2021
research: true
home_tag: "Soft robots"
home_piece: "Flexipod, an untethered soft quadruped that runs at 0.9 m/s and does backflips, with gaits tuned in a CUDA soft-body simulator."
conference: true
publication_short: "ICRA 2021"
doi: 10.1109/ICRA48506.2021.9561018
pdf: /publications/2021-legged-soft-robot/2021-legged-soft-robot.pdf
thumbnail: /publications/2021-legged-soft-robot/flexipod_at_columbia.jpg
code: https://github.com/boxiXia/FlexipodHardware
presentation: "Poster"
featured: true
abstract: "We present Flexipod, an open-source untethered quadrupedal soft robot platform for dynamic locomotion. The robot is 80 vol.% soft with 3D-printed gyroid-infill flexible legs that passively stabilize on multi-terrain environments. With gaits tuned in a CUDA-accelerated soft-body simulator, the real robot achieves 0.9 m/s (2.5 body lengths/sec), faster than most untethered legged soft robots, and can execute backflips."
---

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
  <figcaption>(a) Shore hardness vs. flow rate and infill density. (b, c) 3D printed cross-sections with gyroid infill: (b) 20% infill density and 90% flow rate, (c) 16% infill density and 80% flow rate.</figcaption>
</figure>

## Body Design

The body is printed with flexible material. 96 vol.% of the 3D printed parts are soft, making the robot 80 vol.% soft overall. Soft components are printed with gyroid infill in flexible TPU (20% infill density and 90% flow rate for the body and motor mounts; 16% infill density and 80% flow rate for the legs), with outer skins printed only at mating surfaces to preserve compliance, while the leg adapters and motor shells are printed in rigid polycarbonate (PolyMax PC).

<figure>
  <img src="/publications/2021-legged-soft-robot/body_open.jpg" alt="Soft robot structure" style="width:100%;border-radius:4px">
  <figcaption>Structure of the soft robot: (1) soft main body, (2) camera, (3) electronics, (4) Li-Po battery, (5) bearing, (6) DJI M3508 brushless DC motor in a motor shell, (7) soft leg.</figcaption>
</figure>

<figure>
  <img src="/publications/2021-legged-soft-robot/printed_parts.jpg" alt="3D printed and mechanical components of Flexipod" style="width:100%;border-radius:4px">
  <figcaption>Mechanical components and 3D printed parts: (1) soft leg, (2) leg adapter, (3) outer motor mount, (4) sealed ball bearing (6806-2RS), (5) inner motor mount, (6) DJI M3508 brushless DC motor in a rigid motor shell, (7) top body cover, (8) upper body, (9) lower body.</figcaption>
</figure>

## Soft Leg

The leg's hollowed structure makes it flexible and impact resistant. To demonstrate its damping effect, we dropped the Flexipod from as high as 2.0 m. At impact, the soft legs compressed and the body bent inward to absorb the impact, allowing the robot to recover on its own.

<figure>
  <img src="/publications/2021-legged-soft-robot/leg.jpg" alt="Flexipod soft leg design and drop test" style="width:60%;display:block;margin:0 auto;border-radius:4px">
  <figcaption>(a) Soft leg, leg coupler, and bearing. (b) 3D model of the leg assembly showing its internal structure. (c) Chronophotograph of Flexipod dropped from 2.0 m.</figcaption>
</figure>

## Electrical Design

A Raspberry Pi 4 handles wireless UDP communication and video streaming with the host PC, while a Teensy 4.0 microcontroller runs joint-space position control and state estimation. The Teensy communicates with four DJI C620 ESCs driving the M3508 brushless motors over a CAN bus (via an MCP2551 transceiver) and reads orientation and battery voltage over I²C from an onboard 9-DoF IMU (Adafruit LSM6DSOX + LIS3MDL) and voltage sensor (Adafruit INA260). Power is supplied by a Li-Po battery directly to the ESCs and through a 5 V step-down regulator (Pololu D36V50F5) to the logic electronics.

<figure>
  <img src="/publications/2021-legged-soft-robot/electrical_schematics.png" alt="Electrical system wiring diagram of Flexipod" style="width:100%;border-radius:4px">
  <figcaption>Electrical system and wiring diagram of the Flexipod.</figcaption>
</figure>

## Simulation

We developed a soft robot simulation environment based on [Titan](https://github.com/jacobaustin123/Titan), a CUDA-accelerated massively parallel asynchronous spring-mass simulation library. We extended Titan with a rotational kernel for contact-coupling of soft bodies. The Flexipod simulation achieved 10⁹ spring evaluations per second on a consumer Nvidia 2080Ti GPU.

{{< youtube 52yaNeKdhIc >}}

I also used the simulator to train a soft humanoid with SAC:

{{< youtube 4XBv9BbCrf8 >}}

## Locomotion Patterns

<figure>
  <img src="/publications/2021-legged-soft-robot/gait.jpg" alt="Flexipod locomotion patterns" style="width:100%;border-radius:4px">
  <figcaption>(a) Bounding gait, (b) pace gait, (c) turning, (d) backflip.</figcaption>
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
