---
title: "Omnidirectional Amphibious Locomotion via Internal Mass Actuation"
date: 2026-09-23
authors: ["N. Weaver*", "B. Xia*", "L.-Y. Lo*", "Y. Huang", "B. Chen"]
publication: "arXiv preprint"
year: 2026
preprint: true
featured: true
status: "Preprint"
thumbnail: /publications/2026-marble/MARBLE.jpeg
arxiv: https://arxiv.org/abs/2609.27358
pdf: https://arxiv.org/pdf/2609.27358
website: https://generalroboticslab.com/MARBLE
code: https://github.com/generalroboticslab/MARBLE
abstract: "We present MARBLE, a fully enclosed omnidirectional amphibious rolling robot driven entirely by internal mass redistribution. Three orthogonal linear sliders shift internal masses to roll a sealed spherical shell that serves as ground contact, buoyant hull, and mount for passive fins, so the same mechanism rolls on land and propels itself on water without reconfiguration, and tolerates direct contact with terrain and obstacles."
---

## Abstract

Field robots must traverse varied terrain and obstacles while remaining robust to water, debris, vegetation, and physical contact. We present MARBLE, a fully enclosed omnidirectional amphibious rolling robot driven entirely by internal mass redistribution.

Three mutually orthogonal linear sliders shift internal masses to displace the center of mass and generate body rotation, while an orientation-aware controller maps planar velocity commands into slider positions as the body continuously reorients. A rigid spherical shell encloses all active mechanisms and simultaneously serves as the terrestrial contact surface, buoyant enclosure, and mounting structure for passive fins that enable water-surface propulsion. Rotation of the same shell produces rolling on land and surface propulsion in water without mechanical reconfiguration or separate locomotion actuators.

The spherical morphology further allows the robot to accommodate changes in body orientation and contact location during direct interactions with terrain and obstacles. We evaluate MARBLE through omnidirectional locomotion characterization, traversal across heterogeneous terrestrial environments, aquatic surface locomotion, land-water transitions, and deliberate obstacle interactions. These experiments demonstrate how a single enclosed mechanical architecture can combine omnidirectional mobility, cross-medium locomotion, and tolerance to environmental contact.

## Video

{{< youtube N6Cl5gI0c0U >}}

## Overview

<img src="/publications/2026-marble/teaser_land_to_water.webp" alt="MARBLE rolling from land into water" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

## Cross-Medium Amphibious Locomotion

MARBLE navigates amphibious environments without hardware reconfiguration, using one locomotion system.

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:8px;margin:1em 0">
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Terrestrial Rolling (1.5×)</p>
    <img src="/publications/2026-marble/terrestrial.webp" alt="MARBLE terrestrial rolling" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Water-Surface Propulsion (2×)</p>
    <img src="/publications/2026-marble/aquatic.webp" alt="MARBLE water-surface propulsion" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Land-Water Transition (3×)</p>
    <img src="/publications/2026-marble/transition.webp" alt="MARBLE land-water transition" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
</div>

| | Terrestrial | Aquatic | Transition |
| --- | ---: | ---: | ---: |
| Distance | 10.60 m | 5.24 m | 5.21 m |
| Mean speed | 0.745 ± 0.163 m/s | 0.375 ± 0.059 m/s | 0.215 ± 0.146 m/s |
| Max speed | 1.025 m/s | 0.488 m/s | 0.840 m/s |

## Design

Three orthogonal mass sliders shift MARBLE's center of mass to induce rolling. All active mechanisms are sealed inside the spherical shell.

<img src="/publications/2026-marble/mechanical_design.webp" alt="Mechanical design of MARBLE: linear mass-slider module, internal orthogonal configuration, frame, and sealed shell" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

| Specification | Value |
| --- | --- |
| Outer diameter | 387 mm |
| Shell mass | 1.2 kg |
| Fin height | 8 mm |
| Mass sliders | 3 × 700 g |
| Slider stroke | 220 mm |
| Motors | CubeMars GL40 II |
| Position control | 100 Hz |
| Battery | 4S LiPo, 16 V |

<img src="/publications/2026-marble/locomotion_principle.svg" alt="Locomotion principle of MARBLE" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

## Omnidirectional Velocity Characterization

Geometric and learned controllers in MuJoCo, on ground and on water.

<img src="/publications/2026-marble/sim_controllers.webp" alt="Geometric and learned controllers in simulation, on ground and on water" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

Measured velocity vectors on hardware under joystick commands (7,568 samples each). The learned controller reaches 0.348 m/s mean speed versus 0.252 m/s for the geometric controller.

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:8px;margin:1em 0">
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Learned Controller</p>
    <img src="/publications/2026-marble/velocity_learned.webp" alt="Measured velocity vectors, learned controller" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
  <div>
    <p style="margin:0 0 4px;font-size:0.9em;font-weight:bold">Geometric Controller</p>
    <img src="/publications/2026-marble/velocity_geometric.webp" alt="Measured velocity vectors, geometric controller" style="width:100%;height:auto;display:block;border-radius:4px">
  </div>
</div>

## Obstacle Interaction

The enclosed actuation makes MARBLE contact-tolerant: it can push against obstacles with its shell without exposing any mechanism.

<img src="/publications/2026-marble/buoy_push.webp" alt="MARBLE pushing a floating buoy with the shell" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

<img src="/publications/2026-marble/obstacle_sequence.webp" alt="Obstacle interaction time-lapse: approach, contact, push" style="width:100%;height:auto;display:block;margin:1em 0;border-radius:4px">

## Photos

<div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:8px;margin:1em 0">
  <img src="/publications/2026-marble/land-water-transition.jpg" alt="MARBLE at the land-water boundary" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2026-marble/obstacle-collision.jpg" alt="MARBLE interacting with a buoy" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2026-marble/close-shot.jpg" alt="MARBLE shell and fin close-up" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2026-marble/location-boardwalk.jpg" alt="Pond test site: boardwalk" style="width:100%;height:auto;display:block;border-radius:4px">
  <img src="/publications/2026-marble/location-pavilion.jpg" alt="Pond test site: viewing platform" style="width:100%;height:auto;display:block;border-radius:4px">
</div>

## Links

- [Project Website](https://generalroboticslab.com/MARBLE)
- [Paper (arXiv)](https://arxiv.org/abs/2609.27358)
- [PDF](https://arxiv.org/pdf/2609.27358)
- [Code](https://github.com/generalroboticslab/MARBLE)

## Citation

```bibtex
@misc{weaver2026omnidirectionalamphibiouslocomotion,
      title={Omnidirectional Amphibious Locomotion via Internal Mass Actuation},
      author={Niko Weaver and Boxi Xia and Li-Yu Lo and Yuhao Huang and Boyuan Chen},
      year={2026},
      eprint={2609.27358},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2609.27358},
}
```
