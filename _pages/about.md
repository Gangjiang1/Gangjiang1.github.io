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
    <span class="title"></span>
  </div>

  <div class="llm-terminal__screen">

  <!-- line 1: +1s -->
  <div class="type-line" style="--n:16; --dur:calc(var(--n)*0.035s); --delay:1s;">
    > Gang's Intro:
  </div>

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
  <div class="type-line" style="--n:26; --dur:calc(var(--n)*0.035s); --delay:9.16s;">
    📍 My research interests:
  </div>

  <!-- line 7: +1s -->
  <div class="type-line" style="--n:27; --dur:calc(var(--n)*0.035s); --delay:10.08s;">
    - 🤖 <strong>AI & LLM for Building Science</strong>
  </div>

  <!-- line 8: normal -->
  <div class="type-line" style="--n:39; --dur:calc(var(--n)*0.035s); --delay:11.02s;">
    - ⚙️ <strong>Physics-Informed Machine Learning</strong>
  </div>

  <!-- line 9: normal -->
  <div class="type-line" style="--n:58; --dur:calc(var(--n)*0.035s); --delay:12.39s;">
    - 🏙 <strong>(Urban) Building Energy Modeling & Calibration</strong>.
  </div>

  <!-- line 10: +1s -->
  <div class="type-line" style="--n:88; --dur:calc(var(--n)*0.035s); --delay:14.16s;">
    📌 I'm currently developing <strong>auto-building energy modeling (ABEM) using large language</strong>
  </div>

  <!-- line 11: normal -->
  <div class="type-line" style="--n:71; --dur:calc(var(--n)*0.035s); --delay:17.24s;">
    <strong>models (LLMs)</strong> to improve modeling <strong>accessibility & scalability</strong>.
  </div>

</div>

  <div class="llm-terminal__prompt">
    <span class="prompt">gang@home:~$</span>
    <span class="cursor" aria-hidden="true">█</span>
  </div>
</div>

.prompt-symbol {
  color: #00ff00;
  font-family: 'Courier New', monospace;
  margin-right: 4px;
}

.cursor {
  color: white;
  animation: blink 1s step-start infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}

<style>
.llm-terminal{
  --bg:#0d1117; --fg:#d1d5da; --muted:#8b949e; --accent:#58a6ff;
  border:1px solid #30363d; border-radius:12px; background:var(--bg); color:var(--fg);
  font:14px/1.6 ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  box-shadow:0 12px 30px rgba(0,0,0,.25); overflow:hidden
}
.llm-terminal__bar{display:flex;align-items:center;gap:8px;padding:10px 12px;border-bottom:1px solid #30363d;background:#161b22}
.llm-terminal .dot{width:10px;height:10px;border-radius:50%;display:inline-block}
.llm-terminal .dot.red{background:#ff5f56}.llm-terminal .dot.yellow{background:#ffbd2e}.llm-terminal .dot.green{background:#27c93f}
.llm-terminal .title{color:var(--muted);margin-left:6px;flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.llm-terminal__screen{padding:14px 16px;min-height:260px;white-space:pre-wrap;word-break:break-word;margin:0}
.llm-terminal__prompt{border-top:1px dashed #30363d;padding:10px 16px;color:var(--muted)}
.llm-terminal .prompt{color:var(--accent);margin-right:6px}

/* 核心：纯 CSS 逐字打字（多行） */
.type-line{
  position: relative;
  display:block;
  font-variant-ligatures:none;
  white-space: pre;
  overflow: hidden;
  width: 0ch;
  border-right: 2px solid var(--fg);  /* 初始光标 */
  animation: 
    typing var(--dur) steps(var(--n)) forwards,
    caret var(--dur) steps(1) forwards; /* caret 和 typing 同步，结束后停止 */
  animation-delay: var(--delay), var(--delay);
}
.type-line::before{
  content: attr(data-text);
}

/* 光标动画：typing 过程中闪烁，结束后变透明（隐藏） */
@keyframes caret {
  0%, 49%  { border-right-color: var(--fg); }
  50%, 100%{ border-right-color: transparent; }
}

/* 逐字动画：增长到 n 个字符宽 */
@keyframes typing {
  from { width: 0ch; }
  to   { width: calc(var(--n) * 1ch); }
}

/* 全局暗色方案 */
:root{ color-scheme: dark; }
</style>

## 🖇 Open-Source Contributions

<div style="display: flex; align-items: flex-start; gap: 24px; flex-wrap: wrap;">

<!-- Left Column -->
<div style="flex: 1 1 300px; min-width: 280px;">

<a href="https://github.com/Gangjiang1/EPlus-LLM" target="_blank"><strong>EPlus-LLMv1/v2</strong></a>:  
LLM-driven automatic building energy modeling through natural language.  
<br><br>  
<a href="https://github.com/Gangjiang1/Prompting-for-Auto-building-Modeling" target="_blank"><strong>Prompting LLMs for ABEM</strong></a>:  
A comprehensive guideline for prompt engineering of LLMs in auto-building energy modeling.

</div>

<!-- Right Column -->
<div style="flex: 0 0 420px; text-align: right;">
  <img src="/images/graphic.png" alt="Illustration of LLM for Auto-building modeling" width="420px" style="max-width: 100%; height: auto; border-radius: 10px;">
</div>

</div>

## 🔬 Experience
🧪 As part of my PhD journey, I am working with [Dr. Jianli Chen](https://scholar.google.com/citations?user=Y0ycryUAAAAJ&hl=en) on NSF-funded projects focused on Building Energy Modeling, Calibration, Optimization, and AI Applications in Buildings.

🧫 During my Master’s degree, I collaborated with [Dr. Zhe Tian](https://www.researchgate.net/profile/Zhe-Tian-2) on NSF-China projects related to Building Energy System Simulation and Building Fault Detection & Diagnosis.

✍️ I have completed internships at [Amazon AWS](https://aws.amazon.com/), where I have gained experience in designing and operating data centers with a focus on enhancing resilience and scalability, and at [SUNAC](https://www.sunac.com.cn/en/about.aspx), where I worked in real estate management.

## 🎉 News

📢 Feb. 2026 – I will be attending *ASHRAE Winter Conference* in Las Vegas, NV! See you soon~

📢 Aug. 2025 – I will be speaking at *ASHRAE CIDCO Conference* in Denver, CO! Topic: **Automating Building Energy Modeling from Natural Language** [Slides](/files/2025-cidco-ABEM_NLP.pptx)

📢 Jun. 2025 – I will be attending the *ASHRAE Annual Conference* in Phoenix, Arizona. I am happy to engage in discussions and make connections!

📄 Apr. 2025 – The paper related to the [EPlus-LLMv2 platform](https://doi.org/10.1016/j.autcon.2025.106223), has been accepted for publication in *Automation in Construction*.

📄 Jan. 2025 – Our review paper, [A Review of Physics-Informed Machine Learning for Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.125169), has been published in *Applied Energy*.

📄 Jan. 2025 – My first-authored paper, [Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling](https://doi.org/10.1016/j.energy.2025.134548), has been published in *Energy*.

📄 Jun. 2024 – My first-authored paper, [A Deep Learning-Based Bayesian Framework for High-Resolution Calibration of Building Energy Models](https://doi.org/10.1016/j.enbuild.2024.114755), has been published in *Energy & Buildings*.

📢 Jun. 2024 – I will be speaking about [Natural Language Auto-Modeling via Fine-tuning LLMs](https://www.proquest.com/openview/390f54178cb137415c002b116d3ffe2c/1?pq-origsite=gscholar&cbl=34619) at the *ASHRAE Annual Conference* in Indianapolis, Indiana.

📄 May. 2024 – My first-authored paper, [EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.123431), has been published in *Applied Energy*.

<!-- ## 👀 ![Profile Views](https://komarev.com/ghpvc/?username=Gangjiang1&color=blue&base=1000) -->
