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

{{< lead >}}
{{< clip src="seq-three-objects" eager="true" speed="2" label="Three axes" caption="Closing a jaw pulls the trigger, the separation joint presses the plunger, and fingertip slides twist the cap." steps="3.8:Press trigger|12.1:Rotate plunger|13.8:Press plunger|16.6:Eject tip|21.8:Open cap|28.8:Lift cap|30.2:Close cap" alt="A robot arm with the Cartesian Hand sprays a bottle, uses a pipette, then opens and recloses a centrifuge tube in one run" >}}
<div class="lead-side">
{{< fig src="hand-axes-4x3.jpg" label="Linear axes" caption="Two stacked grippers, four sliding fingertips and the gap between the grippers." alt="Close-up of the hand with arrows along each linear axis" >}}
{{< spec title="Specification" >}}
Fingertip travel | 65&nbsp;mm
Gripper and separation travel | 52&nbsp;mm each
Joint speed | ≈&nbsp;60&nbsp;mm/s
Static hold, one gripper | 2&nbsp;kg
Mass | 850&nbsp;g
Size | ≈&nbsp;166 × 100 × 76&nbsp;mm
Structure | 3D-printed PLA or nylon
Cost | ≈&nbsp;$500
{{< /spec >}}
</div>
{{< /lead >}}

{{< lede >}}The **Cartesian Hand holds one part of an object and moves another**, using only joints that slide in straight lines.{{< /lede >}}

## Abstract

Robotic manipulation has increasingly pursued human-like dexterous hands with many articulated degrees of freedom, offering rich manipulation capabilities at the cost of mechanical and control complexity. At the other extreme, parallel grippers are simple and robust, but provide little ability to manipulate an object after grasping it. Operating articulated objects such as threaded containers, manufacturing tools, and laboratory instruments often requires a second gripper, an external fixture, or coordinated arm motion.

We introduce the Cartesian Hand, a 7-DoF end-effector that rethinks dexterous manipulation by combining independent grasping and relative manipulation within a single end-effector using only linear motion. Two independently actuated parallel grippers hold different parts of an object, while four translating fingertips generate relative motion between the grasped parts. Its configuration-independent fingertip kinematics allow manipulation to be composed from simple linear motion primitives. The Cartesian Hand is particularly suited to objects structured around common mechanisms such as threads, pivots, linear guides, plungers, and triggers.

We demonstrate cap opening and closing, pipetting, pumping, two-handle manipulation, screwdriving, trigger actuation, and in-grasp reorientation across 35 objects spanning laboratory, manufacturing, and household settings. The same manipulation procedures transfer from a fixed-base robot arm to a humanoid, where we demonstrate bimanual laboratory manipulation using two Cartesian Hands. These results show that versatile in-hand manipulation capability can emerge from a mechanically simple architecture when independent grasping and relative motion are designed directly into the end-effector.

## Kinematics

All seven joints are prismatic, so each joint moves its fingertips along a fixed axis, the same way in any configuration and with no singular poses. Each fingertip point is a fixed linear function of the joints, so the Jacobian is a constant matrix of full rank.

{{< row cols="3" wide="true" >}}
{{< clip src="mechanism-exploded" class="framed" label="Inside the hand" caption="The parts that form the two grippers and four sliding fingertips." >}}
{{< clip src="mechanism-joints" speed="2" label="Independent motion" caption="Fingertips slide, jaws open and close, and the two grippers move apart." >}}
{{< clip src="mechanism-workspace" speed="2" label="Workspace in motion" caption="Joint travel changes the hand's opening and fingertip positions." >}}
{{< /row >}}

{{< row cols="2" >}}
{{< fig src="design-cad.jpg" label="Design" caption="Four actuated fingertips, P1 to P4." alt="CAD render of the hand with fingertips P1 to P4 marked" >}}
{{< fig src="design-kinematics.png" label="Joint frames" caption="Seven prismatic joints, each along a fixed axis." alt="Kinematic diagram of the seven prismatic joints" >}}
{{< /row >}}

{{< row cols="2" >}}
{{< fig src="workspace-min.jpg" label="Minimum configuration" alt="Fingertip workspace boxes with the hand closed" >}}
{{< fig src="workspace-max.jpg" label="Maximum configuration" caption="Each fingertip reaches an axis-aligned box: base gripper in orange, auxiliary gripper in blue (mm)." alt="Fingertip workspace boxes with the hand fully open" >}}
{{< /row >}}

## Primitives

Holding or moving the joints, alone or together, gives a small set of linear motions. Compare each one on the physical hand and in simulation.

{{< primgrid data="cartesian_hand.primitives" >}}

## Objects

Objects that share a mechanism share a procedure. A new object keeps the sequence, the controller and the hand, and changes only a few settings such as grasp height, stroke and force limit.

{{< clipgrid data="cartesian_hand.objects" speed="2" filters="lab:Lab|household:Household|manufacturing:Manufacturing" >}}

## Rubik's Cube

{{< clip src="demo-rubik" class="narrow" speed="2" label="Within one grasp" caption="The hand alternates between holding the cube, turning a layer and reorienting it." alt="The hand turns faces of a Rubik's cube and reorients it while holding it" >}}

## On a Humanoid

Two Cartesian Hands on Duke Humanoid v2. One hand opens a centrifuge tube while the other pipettes into it. The arms position the objects and the hands do each operation.

{{< clip src="humanoid-bimanual" class="narrow" speed="2" steps="0:Open cap|11.2:Align tip|16.6:Press plunger|23.1:Return pipette|31:Close cap" label="No shared object" caption="Each hand works its own object, and the arms only position them." alt="A humanoid with a Cartesian Hand on each arm opens a tube, pipettes into it and recaps it" >}}

## Video

{{< youtube ktNcPPTPsQE >}}

## Links

- [Project Website](https://generalroboticslab.com/cartesian_handv1)
- [Paper (arXiv)](https://arxiv.org/abs/2609.25696)
- [PDF](https://arxiv.org/pdf/2609.25696)
- [Code](https://github.com/generalroboticslab/Cartesian_Hand)
- [Open-source hardware](https://github.com/generalroboticslab/Cartesian_Hand/tree/main/hardware)
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
