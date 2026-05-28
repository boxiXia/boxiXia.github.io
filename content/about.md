---
title: "About"
layout: "about"
url: "/about/"
summary: "About me"
---

<style>
.about-section{margin:2rem 0}
.about-section h2{font-size:1rem;font-weight:700;text-transform:uppercase;letter-spacing:.08em;color:var(--secondary);border-bottom:1px solid var(--border);padding-bottom:.4rem;margin-bottom:1.2rem}

/* Timeline */
.timeline{display:flex;flex-direction:column;gap:0;position:relative;padding-left:1.5rem}
.timeline::before{content:"";position:absolute;left:.35rem;top:.4rem;bottom:.4rem;width:2px;background:var(--border)}
.tl-item{position:relative;padding-bottom:1.25rem}
.tl-item:last-child{padding-bottom:0}
.tl-dot{position:absolute;left:-1.15rem;top:.35rem;width:10px;height:10px;border-radius:50%;background:var(--primary);border:2px solid var(--theme);flex-shrink:0}
.tl-period{font-size:.72rem;font-weight:700;text-transform:uppercase;letter-spacing:.06em;color:var(--secondary);margin-bottom:.2rem}
.tl-title{font-size:.95rem;font-weight:600;line-height:1.3;margin-bottom:.15rem}
.tl-sub{font-size:.83rem;color:var(--secondary);line-height:1.4}

/* Expertise tags */
.tag-list{display:flex;flex-wrap:wrap;gap:.4rem;margin:.5rem 0}
.tag{font-size:.75rem;padding:3px 10px;border:1px solid var(--border);border-radius:12px;color:var(--secondary)}

/* Press */
.press-list{display:flex;flex-direction:column;gap:.5rem;margin:.75rem 0 1.5rem}
.press-item{display:flex;align-items:baseline;gap:.75rem;padding:.5rem .75rem;border-left:3px solid var(--border)}
.press-outlet{font-weight:700;min-width:160px;flex-shrink:0;font-size:.9rem}
.press-detail{color:var(--secondary);font-size:.88rem;line-height:1.4}
.press-detail a{color:inherit}
</style>

I'm Boxi Xia, a postdoctoral researcher at Duke University working with Prof. Boyuan Chen in the General Robotics Lab. My research spans the full pipeline from robot hardware design and fabrication through simulation, learning, and real-world deployment — with a focus on legged locomotion systems including humanoids and soft robots.

<div class="about-section">
<h2>Research</h2>

I develop learning-based control algorithms using reinforcement learning and build physics-based simulators to enable efficient robot design and control. Recent projects include designing the Duke Humanoid (a 10-DOF child-sized bipedal robot for energy-efficient locomotion using passive dynamics) and Text2Robot (a framework that uses generative AI to automatically design and manufacture quadrupedal robots from text descriptions). My latest work, Argus, introduces *dynamic symmetry* as a design principle — showing that maximizing the uniformity of a robot's attainable center-of-mass accelerations leads to dramatically improved robustness, agility, and energy efficiency.
</div>

<div class="about-section">
<h2>Areas of Expertise</h2>
<div class="tag-list">
  <span class="tag">Robot hardware design</span>
  <span class="tag">Humanoid & legged locomotion</span>
  <span class="tag">Reinforcement learning</span>
  <span class="tag">Soft robotics & actuators</span>
  <span class="tag">Physics simulation (CUDA, PBD)</span>
  <span class="tag">3D printing & rapid prototyping</span>
  <span class="tag">Deep learning</span>
</div>
</div>

<div class="about-section">
<h2>Experience</h2>
<div class="timeline">
  <div class="tl-item">
    <div class="tl-dot"></div>
    <div class="tl-period">2023 – present</div>
    <div class="tl-title">Postdoctoral Researcher — Duke University</div>
    <div class="tl-sub">General Robotics Lab, advised by Prof. Boyuan Chen. Legged robot design, whole-body control, morphology-varying reinforcement learning.</div>
  </div>
  <div class="tl-item">
    <div class="tl-dot"></div>
    <div class="tl-period">2022 – 2023</div>
    <div class="tl-title">Senior Machine Learning Engineer — XPENG Robotics</div>
    <div class="tl-sub">Santa Clara, CA. Vision-free end-to-end controllers and model-based locomotion controllers for quadrupedal robots.</div>
  </div>
  <div class="tl-item">
    <div class="tl-dot"></div>
    <div class="tl-period">2017 – 2021</div>
    <div class="tl-title">Ph.D. Researcher — Columbia University</div>
    <div class="tl-sub">Creative Machines Lab, advised by Prof. Hod Lipson. Soft robotics, evolutionary computation, and machine learning for robot design.</div>
  </div>
</div>
</div>

<div class="about-section">
<h2>Education</h2>
<div class="timeline">
  <div class="tl-item">
    <div class="tl-dot"></div>
    <div class="tl-period">2021</div>
    <div class="tl-title">Ph.D. in Mechanical Engineering — Columbia University</div>
    <div class="tl-sub">Advisor: Prof. Hod Lipson &nbsp;·&nbsp; Focus: Soft robotics, evolutionary computation, machine learning for robot design</div>
  </div>
  <div class="tl-item">
    <div class="tl-dot"></div>
    <div class="tl-period">2017</div>
    <div class="tl-title">M.S. in Mechanical Engineering (Robotics) — Columbia University</div>
    <div class="tl-sub">Focus: Robotics, control systems, and artificial intelligence</div>
  </div>
  <div class="tl-item">
    <div class="tl-dot"></div>
    <div class="tl-period">2016</div>
    <div class="tl-title">B.Eng. in Machine Design, Manufacturing & Automation — HUST</div>
    <div class="tl-sub">Huazhong University of Science and Technology, Wuhan, China</div>
  </div>
</div>
</div>

<div class="about-section">
<h2>Press & Media Coverage</h2>
<div class="press-list">
  <div class="press-item">
    <span class="press-outlet">Fox News</span>
    <span class="press-detail">Text2Robot: AI automatically designs and 3D-prints walking robots from text descriptions — 2025</span>
  </div>
  <div class="press-item">
    <span class="press-outlet">IEEE Spectrum</span>
    <span class="press-detail">Coverage of Flexipod soft legged robot achieving high-speed locomotion and backflips — 2019</span>
  </div>
  <div class="press-item">
    <span class="press-outlet">Duke University</span>
    <span class="press-detail">Research Spotlight Talk, Responsible AI Symposium — 2025</span>
  </div>
  <div class="press-item">
    <span class="press-outlet">3D Printing & Additive Mfg.</span>
    <span class="press-detail"><a href="https://doi.org/10.1089/3dp.2019.0116">Cover article: Additive manufacturing of silicone composites for soft actuation</a> — 2019</span>
  </div>
  <div class="press-item">
    <span class="press-outlet">Actuators (MDPI)</span>
    <span class="press-detail"><a href="https://doi.org/10.3390/act9030062">Cover article: Improving actuation speed of silicone/ethanol soft actuators</a> — 2020</span>
  </div>
</div>
</div>

<div class="about-section">
<h2>Recognition & Honors</h2>

- Member of Sigma Xi, The Scientific Research Honor Society
- Inventor on provisional patent DU8960PROV (Argusbot), Duke University (2024)
- Active reviewer: IROS, ICRA, CoRL, IEEE RA-L, Springer Nature Journals
</div>

<div class="about-section">
<h2>Contact</h2>

[Email](mailto:boxi.xia@columbia.edu) &nbsp;·&nbsp; [Google Scholar](https://scholar.google.com/citations?user=TjA61pwAAAAJ&hl=en) &nbsp;·&nbsp; [GitHub](https://github.com/boxiXia)
</div>
