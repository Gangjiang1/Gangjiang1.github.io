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

  <div id="llm-output" class="llm-terminal__screen" aria-live="polite"></div>

  <div class="llm-terminal__prompt">
    <span class="prompt">$</span>
    <span>chatgpt.generate("about_gang")</span>
    <span class="cursor" aria-hidden="true"></span>
  </div>

  <!-- 只改这里的 data-text 文案即可；其余代码不要动 -->
  <div id="llm-source" hidden
       data-text="> system
You are an expert model tasked with summarizing Gang Jiang (姜钢).

> user
Introduce yourself for a GitHub about page. Style: confident, research-oriented, minimal fluff, LLM token stream.

> assistant
token_1  identity: PhD candidate @ University of Utah — graduating June 2026. Open to [AP track] [PostDoc] [Industry Research].

token_2  focus: AI & LLM for Buildings; Physics-informed modeling; (Urban) Building Energy Modeling & Calibration.

token_3  now_building: ABEM — auto-building energy modeling with LLMs to boost accessibility & scalability.

token_4  tooling: multi-agent flows, RAG, 8760-h calibration, HPC pipelines.

token_5  impact: lower modeling barriers; faster iteration; better-calibrated decisions.

token_6  interests: building + urban energy, renewables integration, policy-aware analytics.

token_7  links: homepage https://gangjiang1.github.io/ · scholar https://scholar.google.com/citations?user=RGjcgyEAAAAJ · project https://huggingface.co/EPlus-LLM

token_8  contact: reach out for research collab, postdoc, or applied research roles.

✔ ready."></div>
</div>

<noscript>
<p><strong>About me (static):</strong> I’m a third-year PhD candidate at the University of Utah (graduating June 2026). Open to AP track, PostDoc, and industry research roles. Research: AI & LLM for Buildings, Physics-informed modeling, and (Urban) Building Energy Modeling & Calibration. I’m building ABEM—auto-building energy modeling with LLMs—to make modeling more accessible and scalable.</p>
</noscript>

<style>
.llm-terminal{--bg:#0d1117;--fg:#d1d5da;--muted:#8b949e;--accent:#58a6ff;border:1px solid #30363d;border-radius:12px;background:var(--bg);color:var(--fg);font:14px/1.6 ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,"Liberation Mono","Courier New",monospace;box-shadow:0 12px 30px rgba(0,0,0,.25);overflow:hidden}
.llm-terminal__bar{display:flex;align-items:center;gap:8px;padding:10px 12px;border-bottom:1px solid #30363d;background:#161b22}
.llm-terminal .dot{width:10px;height:10px;border-radius:50%;display:inline-block}
.llm-terminal .dot.red{background:#ff5f56}.llm-terminal .dot.yellow{background:#ffbd2e}.llm-terminal .dot.green{background:#27c93f}
.llm-terminal .title{color:var(--muted);margin-left:6px;flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.llm-terminal__screen{padding:14px 16px;min-height:260px;white-space:pre-wrap;word-break:break-word}
.llm-terminal__prompt{border-top:1px dashed #30363d;padding:10px 16px;color:var(--muted)}
.llm-terminal .prompt{color:var(--accent);margin-right:6px}
.cursor{display:inline-block;width:10px;height:1.1em;background:var(--fg);vertical-align:-2px;margin-left:6px;animation:blink 1s steps(1) infinite}
@keyframes blink{0%,49%{opacity:1}50%,100%{opacity:0}}
:root{color-scheme:dark}
</style>

<script type="text/javascript">
(function(){
  // 打字速度（毫秒/字符）——想更快就调小
  var SPEED_MS = 18;

  function start(){
    var out = document.getElementById('llm-output');
    var src = document.getElementById('llm-source');
    if(!out || !src) return;
    var text = src.getAttribute('data-text') || '';
    // 保险：清空再打
    out.textContent = '';
    var i = 0;
    (function type(){
      if(i >= text.length) return;
      out.textContent += text.charAt(i++);
      setTimeout(type, SPEED_MS);
    })();
  }

  // 兼容 GitHub Pages/主题的懒加载或 PJAX：两种事件都监听
  if (document.readyState === 'complete' || document.readyState === 'interactive') {
    setTimeout(start, 0);
  } else {
    document.addEventListener('DOMContentLoaded', start, {once:true});
  }
  // 一些主题用局部导航（如 instant.page / turbolinks），兜底监听 pageshow
  window.addEventListener('pageshow', function(e){
    if (e.persisted) { start(); }
  }, false);
})();
</script>

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
