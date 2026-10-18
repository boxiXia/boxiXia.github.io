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

{{< clip src="tracking" eager="true" wide="true" label="Moving targets" caption="Two independently aimed cameras track two targets carried by two people, with each module's own view alongside." alt="Duke Humanoid v2 tracks two moving targets with its two camera modules while each arm follows one" >}}

{{< lede >}}A humanoid can usually reach far more space than it can see. The **visible-reachable workspace (VRW)** measures the part it can both reach and see, at design time. Applied to this robot, it led to two independently aimed camera modules instead of one shared neck.{{< /lede >}}

## Abstract

Workspace analysis measures where a robot can place its end effector. For visually guided manipulation, reachability alone is insufficient: a kinematically reachable target may not be visible in the specific pose required to reach it. The robot must then redirect its sensing or move its body to acquire a view, turning a perception limitation into additional motion. Existing humanoids largely inherit this limitation when copying human form factors. We introduce the visible-reachable workspace (VRW), a design-stage measure that conditions visibility on feasible reaching configurations and extends it to concurrent visibility of spatially separated work regions. We apply VRW by building a 31-DoF humanoid with independently actuated RGB-D cameras. On the same robot, camera articulation increases visible-reachable coverage from 38% to 97%. With actuated camera layouts, a second camera raises pairwise coverage from 0.45 to 0.95, while a third changes it only to 0.97. In a controlled two-target reach-and-grasp benchmark, our dual-actuated design reduces mean completion time by 17% and mechanical energy by 19% relative to the same robot with its cameras fixed. Hardware experiments demonstrate simultaneous observation and manipulation of front/back and left/right target pairs without torso reorientation. The results suggest that reachability becomes a more informative design quantity for perception-driven humanoid manipulation when it is evaluated together with the sensing configurations that make the reachable space observable. We will open-source all software and the humanoid hardware design.

## The Platform

VRW applies to any embodiment, and this robot is the platform built to study it. Two yaw-pitch camera modules sit on top of the torso, so gaze moves independently of torso heading. The shoulder pitch motor sits inside the torso to keep the shoulders narrow, and the shoulder and elbow ranges allow reaches in front of and behind the body. A whole-body policy sends residual joint-position commands to the legs, arms and cameras.

{{< row cols="2" wide="true" >}}
{{< fig src="platform-cad.jpg" label="The platform as built" caption="(a) Body with its dual-camera head, (b) front view, (c) side view, (d) arm and parallel gripper, (e) lower body, (f) one yaw-pitch camera gimbal. Orange numbers are actuated joints. Green labels are modules: (I) camera, (II) gripper, (III) onboard computer. Dimensions in mm." alt="CAD drawings of Duke Humanoid v2 with joints and modules labeled" >}}
{{< clip src="platform-sweep" speed="3" label="Joint sweep" caption="Every actuated joint driven through its range in one continuous routine." alt="The humanoid moves each joint through its full range" >}}
{{< /row >}}

{{< spec cols="2" wide="true" >}}
Total actuated DoF | 31
Height | 1.2&nbsp;m
Body | 27-DoF
Mass | 36&nbsp;kg
Waist | 1 joint
Arm reach | 0.46&nbsp;m
Legs | 2 × 6-DoF
Leg length | 0.39&nbsp;m
Arms | 2 × 7-DoF
Gripper opening | ≈&nbsp;184&nbsp;mm
Camera head | 2 × 2-DoF gimbal
Camera RGB field of view | 90° × 65°
Policy rate | 50&nbsp;Hz
Camera sensing range | 0.1 to 3.0&nbsp;m
Joint-level PD | 200&nbsp;Hz
Actuator reduction | 7.75:1 to 10:1
Encoders | dual 14-bit
Locomotion sensing | IMU, no foot force sensors
{{< /spec >}}

<details class="more-table"><summary>Per-joint range of motion and maximum torque</summary>

| Joint | ROM (°) | Torque (N·m) | Joint | ROM (°) | Torque (N·m) |
| --- | ---: | ---: | --- | ---: | ---: |
| Waist yaw | [−90, 90] | 60 | Shoulder roll | [−180, 30] | 36 |
| Hip pitch | [−105, 105] | 60 | Shoulder yaw | [−180, 180] | 17 |
| Hip roll | [−105, 30] | 60 | Elbow | [−125, 125] | 17 |
| Hip yaw | [−90, 90] | 60 | Wrist roll | [−180, 180] | 17 |
| Knee | [−130, 130] | 120 | Wrist pitch | [−92, 92] | 14 |
| Ankle pitch | [−50, 50] | 60 | Wrist yaw | [−90, 90] | 5.5 |
| Ankle roll | [−60, 60] | 36 | Camera yaw | [−270, 270] | 5.5 |
| Shoulder pitch | [−108, 108] | 60 | Camera pitch | [−90, 90] | 5.5 |

Left side, mirrored on the right.

</details>

## The Measure

Reachability asks where the arm can put its hand. VRW keeps only the reachable points that a camera can also see from a configuration that achieves the reach. Joints needed for the reach are separated from joints still free to aim a camera, and manipulation takes priority. A wrist camera is modeled too, but its pose is tied to the reaching arm, so it adds no independent gaze. Whatever is left is reachable but blind.

Visible-reachable coverage, η = μ(W<sub>VR</sub>) / μ(W<sub>R</sub>), is the share of reachable volume a camera can see from a configuration that achieves the reach. Pairwise coverage, η₂, measures whether the robot can manipulate at one point while a camera still holds a view of another.

{{< clip src="vrw-fixed-vs-actuated" class="framed" wide="true" label="Same mechanism, different sensing" caption="Visible-reachable workspace of this platform with cameras fixed (left) and actuated (right). Magenta is visible-reachable and blue is reachable but blind." alt="Two voxel workspaces, mostly blue with fixed cameras and almost fully magenta with actuated cameras" >}}

{{< stat from="38%" to="97%" caption="Visible-reachable coverage on this platform with two camera modules, fixed versus actuated." >}}

## Six Embodiments

Under one common geometric evaluation, every external platform shows a gap between what the arms can reach and what the cameras can see. An actuated neck closes more of it than a fixed head. Cameras that share a neck still look in one direction, so concurrent views of two separated regions stay limited.

{{< row cols="3" wide="true" class="vrw-six" >}}
{{< clip src="vrw-ours" class="framed" caption="<strong>This platform</strong>" alt="Visible-reachable workspace of Duke Humanoid v2" >}}
{{< clip src="vrw-g1" class="framed" caption="Unitree G1" alt="Visible-reachable workspace of Unitree G1" >}}
{{< clip src="vrw-t1" class="framed" caption="Booster T1" alt="Visible-reachable workspace of Booster T1" >}}
{{< clip src="vrw-apollo" class="framed" caption="Apptronik Apollo" alt="Visible-reachable workspace of Apptronik Apollo" >}}
{{< clip src="vrw-gr3" class="framed" caption="Fourier GR-3" alt="Visible-reachable workspace of Fourier GR-3" >}}
{{< clip src="vrw-talos" class="framed" caption="PAL TALOS" alt="Visible-reachable workspace of PAL TALOS" >}}
{{< /row >}}

| Platform | Camera articulation | Visible | VR / reachable volume | Pairwise η₂ |
| --- | --- | ---: | ---: | ---: |
| **This platform, actuated** | 2 × 2-DoF gimbals | **97%** | 1.357 / 1.402 m³ | **96%** |
| Unitree G1 | fixed head | 16% | 0.136 / 0.879 m³ | 3% |
| Booster T1 | 2-DoF neck | 67% | 0.734 / 1.094 m³ | 20% |
| Apptronik Apollo | 3-DoF neck | 76% | 0.840 / 1.109 m³ | 25% |
| Fourier GR-3 | 2-DoF neck | 70% | 1.092 / 1.567 m³ | 24% |
| PAL TALOS | 2-DoF neck | 48% | 0.923 / 1.930 m³ | 9% |

External models come from public simulation repositories. None of the external platforms can aim two camera views independently. Different embodiments induce different evaluation volumes, so these values are context and not a ranking.

## Two-Target Reach and Grasp

The benchmark ran in physics simulation with the same whole-body policy and the same target-discovery planner for every camera configuration. Success rates were similar across all five configurations, but the time and energy needed were not. The actuated configurations spend much less time searching, because the robot finds a target by moving its cameras instead of walking until the target comes into view.

| Configuration | Time (s) | Search (s) | Approach (s) | Manipulation (s) | Energy (J) |
| --- | ---: | ---: | ---: | ---: | ---: |
| Unitree G1 | 27.5 | 3.8 | 3.8 | 19.9 | 494 |
| Fix₁ | 20.5 | 3.3 | 3.3 | 13.9 | 595 |
| Act₁ | 15.5 | 0.6 | 2.7 | 12.2 | 385 |
| Fix₂ | 17.0 | 0.2 | 3.2 | 13.6 | 425 |
| **Act₂ (ours)** | **14.1** | **0.1** | **2.1** | **11.9** | **346** |

Act₂ against Fix₂: time −17%, energy −19%, search time −50%. Act₁ against Fix₁: time −24%, energy −35%, search time −82%. Values are success-conditional means over six scenarios, 30 trials per scenario (ten seeded layouts, three replicates each). Lower is better. Success rates ranged from 0.967 to 0.994.

All six scenarios under the four camera configurations. Shaded cones are the camera fields of view and green cubes are the targets.

{{< row cols="2" wide="true" >}}
{{< clip src="sim-lr-close" quad="Single fixed|Single actuated|Dual fixed|Dual actuated" label="Left and right, close" caption="Only the actuated pair keeps both targets in view and reaches both." >}}
{{< clip src="sim-fb-close" quad="Single fixed|Single actuated|Dual fixed|Dual actuated" label="Front and behind, close" caption="A separation that a single forward view cannot span." >}}
{{< clip src="sim-lr-far" quad="Single fixed|Single actuated|Dual fixed|Dual actuated" label="Left and right, far" caption="Benches at 0.8 m, so the robot walks before reaching." >}}
{{< clip src="sim-fb-far" quad="Single fixed|Single actuated|Dual fixed|Dual actuated" label="Front and behind, far" caption="Finding a target before walking is what shortens the approach." >}}
{{< clip src="sim-lr-human" quad="Single fixed|Single actuated|Dual fixed|Dual actuated" label="Handoff, left and right" caption="One target on a bench, the other held by a person." >}}
{{< clip src="sim-fb-human" quad="Single fixed|Single actuated|Dual fixed|Dual actuated" label="Handoff, front and behind" caption="The same mix with the two regions fore and aft." >}}
{{< /row >}}

## On Hardware

We deployed the adopted configuration on the physical robot. With targets in reach, the two cameras observed a front/back pair and a left/right pair, and both arms grasped them without turning the torso. With targets out of reach, the robot located both first, then walked closer and grasped them. Each clip plays four trials together.

{{< row cols="2" wide="true" >}}
{{< clip src="real-lr-close" label="Left and right, within reach" caption="The two cameras observe the separated targets and both arms reach without turning the torso." >}}
{{< clip src="real-fb-close" label="Front and behind" caption="The region a single forward-facing view cannot cover." >}}
{{< clip src="real-lr-far" label="Left and right, out of reach" caption="The robot observes both targets, walks closer, then grasps." >}}
{{< clip src="real-fb-far" label="Front and behind, out of reach" caption="The same walk-then-grasp with the targets separated along the other axis." >}}
{{< /row >}}

### Continuous Operation

{{< clip src="walk-continuous" manual="true" speed="2" wide="true" label="One unbroken take" caption="About five minutes of walking without a cut, shown at twice speed with both synchronized camera views in one frame. Press play to watch with sound." alt="Duke Humanoid v2 walking continuously, two camera views side by side" >}}

## Video

{{< youtube tKMAzhqL58o >}}

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
