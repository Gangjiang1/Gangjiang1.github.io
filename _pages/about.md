---
permalink: /
title: "👋🏼 Hi there, I'm Gang!"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

![Illustration of LLM for Auto-building modeling](/images/graphic.png){: .align-right width="420px"}

<div class="llm-terminal" role="region" aria-label="LLM terminal introduction">
  <div class="llm-terminal__bar">
    <span class="dot red"></span><span class="dot yellow"></span><span class="dot green"></span>
    <span class="title">gang@about.md — llm run</span>
  </div>

  <div class="llm-terminal__screen">
    <!-- 一行一行逐字打印（已精确计算长度 --n），只改 data-text；若改了内容同步改 --n -->
    <div class="type-line" data-text="> system"                                   style="--n:8;  --dur:calc(var(--n)*0.035s); --delay:0s;"></div>
    <div class="type-line" data-text="You are an expert model summarizing Gang Jiang (姜钢)." style="--n:53; --dur:calc(var(--n)*0.035s); --delay:0.40s;"></div>

    <div class="type-line" data-text="> user"                                     style="--n:6;  --dur:calc(var(--n)*0.035s); --delay:2.375s;"></div>
    <div class="type-line" data-text="Introduce yourself in an LLM token-stream style."        style="--n:48; --dur:calc(var(--n)*0.035s); --delay:2.705s;"></div>

    <div class="type-line" data-text="> assistant"                                style="--n:11; --dur:calc(var(--n)*0.035s); --delay:4.505s;"></div>
    <div class="type-line" data-text="token_1  identity: PhD candidate @ University of Utah — June 2026." style="--n:66; --dur:calc(var(--n)*0.035s); --delay:5.01s;"></div>
    <div class="type-line" data-text="token_2  focus: AI & LLM for Buildings; Physics-informed; Urban BEM & Calibration." style="--n:82; --dur:calc(var(--n)*0.035s); --delay:7.44s;"></div>
    <div class="type-line" data-text="token_3  now_building: ABEM — auto-building energy modeling with LLMs." style="--n:70; --dur:calc(var(--n)*0.035s); --delay:10.43s;"></div>
    <div class="type-line" data-text="token_4  tooling: multi-agent flows; RAG; 8760-h calibration; HPC pipelines." style="--n:76; --dur:calc(var(--n)*0.035s); --delay:13.00s;"></div>
    <div class="type-line" data-text="token_5  impact: lower barriers; faster iteration; better-calibrated decisions." style="--n:79; --dur:calc(var(--n)*0.035s); --delay:15.78s;"></div>
    <div class="type-line" data-text="token_6  links: homepage gangjiang1.github.io · scholar Google Scholar · project EPlus-LLM" style="--n:90; --dur:calc(var(--n)*0.035s); --delay:18.665s;"></div>
    <div class="type-line" data-text="token_7  contact: open to AP track, PostDoc, and industry research roles." style="--n:73; --dur:calc(var(--n)*0.035s); --delay:21.935s;"></div>
  </div>

  <div class="llm-terminal__prompt">
    <span class="prompt">$</span>
    <span>chatgpt.generate("about_gang")</span>
    <span class="cursor" aria-hidden="true"></span>
  </div>
</div>

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
  white-space: pre;          /* 精准按字符宽度计算 */
  overflow: hidden;
  width: 0ch;               /* 从 0 个字符开始 */
  border-right: 2px solid var(--fg);  /* 光标 */
  /* 两个动画：typing 为逐字，caret 为光标闪烁 */
  animation: typing var(--dur) steps(var(--n)) forwards,
             caret 1s steps(1) infinite;
  animation-delay: var(--delay), var(--delay);
}
.type-line::before{
  content: attr(data-text);
}

/* 光标闪烁 */
@keyframes caret {
  0%,49%  { border-right-color: var(--fg); }
  50%,100%{ border-right-color: transparent; }
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
[EPlus-LLMv1/v2](https://github.com/Gangjiang1/EPlus-LLM): LLM-driven automatic building energy modeling through natural language.

[Prompting LLMs for ABEM](https://github.com/Gangjiang1/Prompting-for-Auto-building-Modeling): A comprehensive guideline for prompt engineering of LLMs in auto-building energy modeling.

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
