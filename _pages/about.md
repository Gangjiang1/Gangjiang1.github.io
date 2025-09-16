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
    <div class="controls">
      <button id="llm-toggle" aria-pressed="false" title="Pause/Resume">⏯</button>
      <button id="llm-replay" title="Replay">↺</button>
      <label class="speed">⚡
        <input id="llm-speed" type="range" min="0" max="100" value="50" aria-label="Streaming speed">
      </label>
    </div>
  </div>
  <div id="llm-output" class="llm-terminal__screen" aria-live="polite"></div>
  <div class="llm-terminal__prompt">
    <span class="prompt">$</span>
    <span>chatgpt.generate(</span><span class="param">"about_gang"</span><span>)</span>
    <span class="cursor" aria-hidden="true"></span>
  </div>
</div>

<noscript>
<p><strong>About me (static):</strong> I’m a third-year PhD candidate at the University of Utah (graduating June 2026). Open to AP track, PostDoc, and industry research roles. Research: AI & LLM for Buildings, Physics-informed modeling, and (Urban) Building Energy Modeling & Calibration. I’m building ABEM—auto-building energy modeling with LLMs—to make modeling more accessible and scalable.</p>
</noscript>

<style>
.llm-terminal{--bg:#0d1117;--fg:#d1d5da;--muted:#8b949e;--accent:#58a6ff;--ok:#3fb950;--warn:#d29922;--err:#f85149; border:1px solid #30363d;border-radius:12px;background:var(--bg);color:var(--fg);font:14px/1.6 ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,"Liberation Mono","Courier New",monospace;box-shadow:0 12px 30px rgba(0,0,0,.25);overflow:hidden}
.llm-terminal__bar{display:flex;align-items:center;gap:8px;padding:10px 12px;border-bottom:1px solid #30363d;background:#161b22;position:relative}
.llm-terminal .dot{width:10px;height:10px;border-radius:50%;display:inline-block}
.llm-terminal .dot.red{background:#ff5f56}.llm-terminal .dot.yellow{background:#ffbd2e}.llm-terminal .dot.green{background:#27c93f}
.llm-terminal .title{color:var(--muted);margin-left:6px;flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.llm-terminal .controls{display:flex;gap:6px;align-items:center}
.llm-terminal button{background:#21262d;border:1px solid #30363d;border-radius:8px;color:var(--fg);padding:4px 8px;cursor:pointer}
.llm-terminal button:hover{background:#2b3139}
.llm-terminal .speed{display:flex;align-items:center;gap:6px;color:var(--muted);font-size:12px}
.llm-terminal input[type="range"]{accent-color:var(--accent)}
.llm-terminal__screen{padding:14px 16px;min-height:260px;white-space:pre-wrap;word-break:break-word}
.llm-terminal__prompt{border-top:1px dashed #30363d;padding:10px 16px;color:var(--muted)}
.llm-terminal .prompt{color:var(--accent);margin-right:6px}
.cursor{display:inline-block;width:10px;height:1.1em;background:var(--fg);vertical-align:-2px;margin-left:6px;animation:blink 1s steps(1) infinite}
@keyframes blink{0%,49%{opacity:1}50%,100%{opacity:0}}
.token-key{color:#a5d6ff}
.token-str{color:#7ee787}
.token-emph{color:#ffdf85}
.token-badge{background:#1f6feb;color:#fff;border-radius:10px;padding:0 6px;margin:0 2px;font-size:12px}
.badge{display:inline-block;border:1px solid #30363d;border-radius:20px;padding:2px 8px;margin:0 4px 0 0;color:var(--muted)}
.link{color:var(--accent);text-decoration:none;border-bottom:1px dashed #30363d}
.link:hover{border-bottom-color:var(--accent)}
:root{color-scheme:dark}
</style>

<script>
(function(){
  const out = document.getElementById('llm-output');
  const toggleBtn = document.getElementById('llm-toggle');
  const replayBtn = document.getElementById('llm-replay');
  const speed = document.getElementById('llm-speed');

  // Streaming content (token-like chunks)
  const stream = [
    {t:"> system", cls:"token-key"},
    "\nYou are an expert model tasked with summarizing ",
    {t:"Gang Jiang", cls:"token-emph"},
    " (姜钢).\n\n",
    {t:"> user", cls:"token-key"},
    "\nIntroduce yourself succinctly for a GitHub about page. Style: confident, research-oriented, minimal fluff, token-stream.\n\n",
    {t:"> assistant", cls:"token-key"},
    "\n",
    {t:"token_1", cls:"badge"}, "  ", {t:"identity:", cls:"token-key"},
    " PhD candidate @ University of Utah — graduating ",
    {t:"June 2026", cls:"token-emph"}, ". Open to ",
    {t:"AP track", cls:"token-badge"}, " ",
    {t:"PostDoc", cls:"token-badge"}, " ",
    {t:"Industry Research", cls:"token-badge"}, ".\n\n",

    {t:"token_2", cls:"badge"}, "  ", {t:"focus:", cls:"token-key"},
    " AI & LLM for Buildings; Physics-informed modeling; ",
    "(Urban) Building Energy Modeling & Calibration.\n",

    {t:"token_3", cls:"badge"}, "  ", {t:"now_building:", cls:"token-key"},
    " ABEM — auto-building energy modeling with LLMs to boost ",
    "accessibility and scalability.\n",

    {t:"token_4", cls:"badge"}, "  ", {t:"tooling:", cls:"token-key"},
    " multi-agent flows, retrieval, calibration at 8760-h resolution, HPC pipelines.\n",

    {t:"token_5", cls:"badge"}, "  ", {t:"impact:", cls:"token-key"},
    " lower modeling barriers; faster iteration; better calibrated decisions.\n\n",

    {t:"token_6", cls:"badge"}, "  ", {t:"interests:", cls:"token-key"},
    " building+urban energy, renewables integration, policy-aware analytics.\n",

    {t:"token_7", cls:"badge"}, "  ", {t:"links:", cls:"token-key"},
    " homepage ",
    {t:"gangjiang1.github.io", cls:"link", href:"https://gangjiang1.github.io/"},
    " · scholar ",
    {t:"Google Scholar", cls:"link", href:"https://scholar.google.com/citations?user=RGjcgyEAAAAJ&hl=en"},
    " · project ",
    {t:"EPlus-LLM", cls:"link", href:"https://huggingface.co/EPlus-LLM"},
    ".\n\n",

    {t:"token_8", cls:"badge"}, "  ", {t:"contact:", cls:"token-key"},
    " reach out for research collab, postdoc, or applied research roles.\n",

    "\n", {t:"✔ ready.", cls:"token-emph"}
  ];

  let i = 0, paused = false, handle = null;

  function speedMs(){
    // Map 0..100 -> 60..5 ms per token step
    const v = Number(speed.value||50);
    return 60 - Math.round(v*0.55);
  }

  function renderChunk(chunk){
    if(typeof chunk === 'string'){ out.append(chunk); return; }
    const span = document.createElement(chunk.href ? 'a' : 'span');
    span.textContent = chunk.t;
    if(chunk.cls) span.className = chunk.cls;
    if(chunk.href){ span.href = chunk.href; span.target = "_blank"; rel="noopener"; }
    out.appendChild(span);
  }

  function tick(){
    if(paused) return;
    if(i >= stream.length){ clearInterval(handle); return; }
    renderChunk(stream[i++]);
  }

  function play(){
    paused = false;
    clearInterval(handle);
    handle = setInterval(tick, speedMs());
    toggleBtn.setAttribute('aria-pressed','true');
  }
  function pause(){
    paused = true;
    clearInterval(handle);
    toggleBtn.setAttribute('aria-pressed','false');
  }

  toggleBtn?.addEventListener('click', ()=> paused ? play() : pause());
  replayBtn?.addEventListener('click', ()=>{
    pause();
    out.textContent = '';
    i = 0;
    play();
  });
  speed?.addEventListener('input', ()=>{
    if(!paused){ play(); }
  });

  // Autoplay on first paint
  play();
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
