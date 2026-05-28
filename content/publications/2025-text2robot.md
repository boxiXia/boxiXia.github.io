---
title: "Text2Robot: Evolutionary robot design from text descriptions"
date: 2025-05-01
authors: ["R.P. Ringel", "Z.S. Charlick", "J. Liu", "B. Xia", "B. Chen"]
publication: "2025 IEEE International Conference on Robotics and Automation (ICRA)"
pages: "5789–5797"
year: 2025
conference: true
featured: true
publication_short: "ICRA 2025"
doi: 10.1109/ICRA55743.2025.11128168
arxiv: https://arxiv.org/abs/2406.19963
pdf: /publications/2025-text2robot/2025-text2robot.pdf
website: https://generalroboticslab.com/Text2Robot
code: https://github.com/generalroboticslab/Text2Robot
thumbnail: /publications/2025-text2robot/text2robot_Fig_Teaser.png
presentation: "Poster"
abstract: "Text2Robot converts user text descriptions into physical quadrupedal robots. Within minutes, text-to-3D models initialize diverse morphologies; within a day, geometric processing and body-control co-optimization produce a walking robot that accounts for real-world electronics and manufacturability. The framework enables rapid prototyping and opens new opportunities for generative robot design."
---

## Abstract

Robot design has traditionally been costly and labor-intensive. Despite advancements in automated processes, it remains challenging to navigate a vast design space while producing physically manufacturable robots. We introduce Text2Robot, a framework that converts user text specifications and performance preferences into physical quadrupedal robots. Within minutes, Text2Robot can use text-to-3D models to provide strong initializations of diverse morphologies. Within a day, our geometric processing algorithms and body-control co-optimization produce a walking robot by explicitly considering real-world electronics and manufacturability. Text2Robot enables rapid prototyping and opens new opportunities for robot design with generative models. Our website is at http://generalroboticslab.com/Text2Robot/.

{{< youtube Cwq7G6OUeGg >}}

## Pipeline

<figure>
  <img src="/publications/2025-text2robot/text2robot_Fig_Pipeline.png" alt="Text2Robot pipeline" style="width:100%;border-radius:4px">
  <figcaption>Overview of the four steps in the Text2Robot framework: (1) text-to-3D mesh generation, (2) geometric processing into kinetic robot model, (3) evolutionary co-optimization of morphology and policy, (4) physical fabrication and assembly.</figcaption>
</figure>

## Evolutionary Co-optimization

<figure>
  <img src="/publications/2025-text2robot/text2robot_EvolutionaryLoop.PNG" alt="Evolutionary loop diagram" style="width:100%;border-radius:4px">
  <figcaption><strong>Morphology and Walking Policy Co-optimization.</strong> (A) The inner loop implements reinforcement learning to optimize the robot control policy; the outer loop optimizes robot morphologies through genetic operations. (B) Genetic representation and examples of crossover and mutation.</figcaption>
</figure>

## Generated Robot Designs

<figure>
  <img src="/publications/2025-text2robot/text2robot_BankGraphic.PNG" alt="Generated robot meshes" style="width:100%;border-radius:4px">
  <figcaption><strong>Generated Meshes and Corresponding User Descriptions.</strong> (A) Sixteen robot mesh models generated from diverse user text descriptions. (B) Morphology variants for bug, frog, and dog robots generated from similar prompts.</figcaption>
</figure>

## Paper

<object data="/publications/2025-text2robot/2025-text2robot.pdf" type="application/pdf" width="100%" height="800px" style="border:none;"><p>PDF cannot be displayed. <a href="/publications/2025-text2robot/2025-text2robot.pdf">Download PDF</a></p></object>

## Links

- [Download PDF](/publications/2025-text2robot/2025-text2robot.pdf)
- [Full text (IEEE Xplore)](https://ieeexplore.ieee.org/document/11128168)
- [Open access (arXiv)](https://arxiv.org/abs/2406.19963)

## Citation

```bibtex
@inproceedings{ringel2025text2robot,
  title={Text2Robot: Evolutionary robot design from text descriptions},
  author={Ringel, R.P. and Charlick, Z.S. and Liu, J. and Xia, B. and Chen, B.},
  booktitle={2025 IEEE International Conference on Robotics and Automation (ICRA)},
  pages={5789--5797},
  year={2025},
  organization={IEEE}
}
```
