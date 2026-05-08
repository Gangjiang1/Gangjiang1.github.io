---
permalink: /
title: "👋🏼 Hi there, I'm Gang!"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<div class="llm-terminal" role="region" aria-label="LLM terminal introduction">
  <div class="llm-terminal__bar">
    <span class="dot red"></span><span class="dot yellow"></span><span class="dot green"></span>
    <span class="title">Terminal</span>
  </div>

  <div class="llm-terminal__screen">
    <!-- line 2: +1s -->
    <div class="type-line" style="--n:94; --dur:calc(var(--n)*0.035s); --delay:1.56s;">
      👨🏻‍💻 I'm a fourth-year PhD candidate at The University of Utah, expecting to graduate in
    </div>

    <!-- line 3: normal -->
    <div class="type-line" style="--n:12; --dur:calc(var(--n)*0.035s); --delay:4.85s;">
      June 2026.
    </div>

    <!-- line 4: +1s -->
    <div class="type-line" style="--n:81; --dur:calc(var(--n)*0.035s); --delay:5.23s;">
      I am open to work, including <strong>AP track, PostDoc, and industry research positions</strong>.
    </div>

    <!-- line 5: normal -->
    <div class="type-line" style="--n:31; --dur:calc(var(--n)*0.035s); --delay:8.07s;">
      Please feel free to reach out!
    </div>

    <!-- line 6: +1s -->
    <div class="type-line" style="--n:26; --dur:calc(var(--n)*0.035s); --delay:9.0s;">
      📍 My research interests:
    </div>

    <!-- line 7: +1s -->
    <div class="type-line" style="--n:40; --dur:calc(var(--n)*0.035s); --delay:10.0s;">
      - 🤖 <strong>AI & LLM for Building Science</strong>
    </div>

    <!-- line 8: normal -->
    <div class="type-line" style="--n:45; --dur:calc(var(--n)*0.035s); --delay:11.5s;">
      - ⚙️ <strong>Physics-Informed & Automated Modeling</strong>
    </div>

    <!-- line 9: normal -->
    <div class="type-line" style="--n:58; --dur:calc(var(--n)*0.035s); --delay:13.39s;">
      - 🏙 <strong>(Urban) Building Sustainability & Resilience</strong>
    </div>

    <!-- line 10: +1s -->
    <div class="type-line" style="--n:88; --dur:calc(var(--n)*0.035s); --delay:15.16s;">
      📌 I'm developing <strong>auto-building energy modeling (ABEM) using large language models</strong>
    </div>

    <!-- line 11: normal -->
    <div class="type-line" style="--n:71; --dur:calc(var(--n)*0.035s); --delay:18.24s;">
      <strong>(LLMs)</strong> to improve modeling <strong>accessibility & scalability</strong>.
    </div>

  </div>

  <div class="llm-terminal__prompt">
    <span class="prompt-symbol">gang@home:~$</span>
    <span class="cursor" aria-hidden="true">█</span>
  </div>
</div>

<style>
/* -------------------- Terminal UI Styling -------------------- */
.llm-terminal {
  --bg: #ffffff;
  --fg: #24292f;
  --muted: #6e7781;
  --accent: #0969da;

  border: 1px solid #d0d7de;
  border-radius: 12px;
  background: var(--bg);
  color: var(--fg);
  font: 14px/1.6 ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.08);
  overflow: hidden;
}

.llm-terminal__bar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 12px;
  border-bottom: 1px solid #d0d7de;
  background: #f6f8fa;
}

.llm-terminal .dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  display: inline-block;
}

.llm-terminal .dot.red {
  background: #ff5f56;
}
.llm-terminal .dot.yellow {
  background: #ffbd2e;
}
.llm-terminal .dot.green {
  background: #27c93f;
}

.llm-terminal .title {
  color: var(--muted);
  margin-left: 6px;
  flex: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.llm-terminal__screen {
  padding: 14px 16px;
  min-height: 260px;
  white-space: pre-wrap;
  word-break: break-word;
  margin: 0;
}

.llm-terminal__prompt {
  border-top: 1px dashed #d0d7de;
  padding: 10px 16px;
  color: var(--muted);
}

.prompt-symbol {
  color: #1a7f37; 
}

.cursor {
  color: #24292f;
  animation: blink 1s step-start infinite;
}

@keyframes blink {
  50% {
    opacity: 0;
  }
}

/* -------------------- Typewriter Effect -------------------- */
.type-line {
  position: relative;
  display: block;
  font-variant-ligatures: none;
  white-space: pre;
  overflow: hidden;
  width: 0ch;
  border-right: 2px solid #57606a;
  animation:
    typing var(--dur) steps(var(--n)) forwards,
    caret var(--dur) steps(1) forwards;
  animation-delay: var(--delay), var(--delay);
}

@keyframes caret {
  0%, 49% {
    border-right-color: var(--fg);
  }
  50%, 100% {
    border-right-color: transparent;
  }
}

@keyframes typing {
  from {
    width: 0ch;
  }
  to {
    width: calc(var(--n) * 1ch);
  }
}

/* Global dark mode hint */
:root {
  color-scheme: dark;
}
</style>

## 🖇 Open-Source Contributions

<div style="display: flex; align-items: flex-start; gap: 24px; flex-wrap: wrap;">

<!-- Left Column -->
<div style="flex: 1 1 300px; min-width: 280px;">
<br>  
<a href="https://github.com/Gangjiang1/EPlus-LLM" target="_blank"><strong>EPlus-LLMv1/v2</strong></a>:  
LLM-driven automatic building energy modeling through natural language.  
<br><br>  
<a href="https://github.com/Gangjiang1/Prompting-for-Auto-building-Modeling" target="_blank"><strong>Prompting LLMs for ABEM</strong></a>:  
A comprehensive guideline for prompt engineering of LLMs in auto-building energy modeling.
</div>

<!-- Right Column -->
<div style="flex: 0 0 420px; text-align: right;">
  <figure style="margin: 0;">
    <img src="/images/graphic.png" alt="Illustration of LLM for Auto-building modeling" width="420px" style="max-width: 100%; height: auto; border-radius: 10px;">
    <figcaption style="font-size: 14px; color: #666; margin-top: 8px; padding-left: 1.5em;">
      <em>Figure: LLM-Powered Auto-Building Modeling Workflow</em>
    </figcaption>
  </figure>
</div>
</div>

## 🔬 Experience
🚀 Currently, I am collaborating with [Dr. Shandian Zhe](https://users.cs.utah.edu/~zhe/) (School of Computing, University of Utah) on NSF projects focused on improving LLMs' accuracy, computational efficiency, and robustness.

🧪 As part of my PhD journey, I am working with [Dr. Jianli Chen](https://scholar.google.com/citations?user=Y0ycryUAAAAJ&hl=en) on NSF-funded projects focused on Building Energy Modeling, Calibration, Optimization, and AI Applications in Buildings.

🧫 During my Master’s degree, at Tianjin University, I collaborated with [Dr. Zhe Tian](https://www.researchgate.net/profile/Zhe-Tian-2) on NSF-China projects related to Building Energy System Simulation and Building Fault Detection & Diagnosis.

✍️ I have completed internships at [Amazon AWS](https://aws.amazon.com/), where I have gained experience in designing and operating data centers with a focus on enhancing resilience and scalability, and at [SUNAC](https://www.sunac.com.cn/en/about.aspx), where I worked in real estate management.

## 🎉 News
🚀 My first-authored research paper, [Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling](https://doi.org/10.1016/j.energy.2025.134548), (*Energy, 2025*), has been recognized as a **🏆 Top 1% Highly Cited Paper** by ESI.

🚀 My first-authored research paper, [EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.123431), (*Applied Energy, 2024*), has also been selected as a **🏆 Top 1% Highly Cited Paper** and a **🔥 Top 0.1% Hot Cited Paper** by ESI.

📄 Dec. 2025 – First-authored paper, [Benchmarking Knowledge and Capability of Large Language Models in Building Science Domain](https://doi.org/10.59717/ipj.energy-use.2025.100026), has been published in *Energy Use*.

📢 Jun. 2025 – I will be attending the *ASHRAE Annual Conference* in Phoenix, Arizona. I am happy to engage in discussions and make connections!

📄 Apr. 2025 – The paper related to the [EPlus-LLMv2 platform](https://doi.org/10.1016/j.autcon.2025.106223), has been accepted for publication in *Automation in Construction*.

📄 Jan. 2025 – Our review paper, [A Review of Physics-Informed Machine Learning for Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.125169), has been published in *Applied Energy*.

📄 Jan. 2025 – My first-authored paper, [Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling](https://doi.org/10.1016/j.energy.2025.134548), has been published in *Energy*.

📄 Jun. 2024 – My first-authored paper, [A Deep Learning-Based Bayesian Framework for High-Resolution Calibration of Building Energy Models](https://doi.org/10.1016/j.enbuild.2024.114755), has been published in *Energy & Buildings*.

📄 May. 2024 – My first-authored paper, [EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.123431), has been published in *Applied Energy*.

## 🗣️ Talks
🎤 Feb. 2026 – I’m excited to attend the *ASHRAE Winter Conference* in Las Vegas, NV! Looking forward to connecting with you there! 🌆  
I’ll be giving two presentations:  
(1) Large language models for automated building energy modeling (**Invited Talk**)  
(2) Real-world applications of the EPlus-LLM Platform (**Paper Session, Poster**)

🎤 Oct. 2025 – **Online talk** on BuildNext: Toward Automated Building Energy Modeling with Large Language Models [Slides](/files/Gang_LLM_ABEM_Slides.pdf)

🎤 Aug. 2025 – I was invited to give a talk at *ASHRAE CIDCO Conference* in Denver, CO! Topic: **Automating Building Energy Modeling from Natural Language**

🎤 Jun. 2024 – I will be speaking about [Natural Language Auto-Modeling via Fine-tuning LLMs](https://www.proquest.com/openview/390f54178cb137415c002b116d3ffe2c/1?pq-origsite=gscholar&cbl=34619) at the *ASHRAE Annual Conference* in Indianapolis, Indiana.
