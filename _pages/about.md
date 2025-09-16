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
</div>

<noscript>
<p><strong>About me (static):</strong> I’m a third-year PhD candidate at the University of Utah (graduating June 2026). Open to AP track, PostDoc, and industry research roles. Research: AI & LLM for Buildings, Physics-informed modeling, and (Urban) Building Energy Modeling & Calibration. I’m building ABEM—auto-building energy modeling with LLMs—to make modeling more accessible and scalable.</p>
</noscript>

<style>
.llm-terminal{--bg:#0d1117;--fg:#d1d5da;--muted:#8b949e;--accent:#58a6ff;--ok:#3fb950;--warn:#d29922;--err:#f85149; border:1px solid #30363d;border-radius:12px;background:var(--bg);color:var(--fg);font:14px/1.6 ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,"Liberation Mono","Courier New",monospace;box-shadow:0 12px 30px rgba(0,0,0,.25);overflow:hidden}
.llm-terminal__bar{display:flex;align-items:center;gap:8px;padding:10px 12px;border-bottom:1px solid #30363d;background:#161b22}
.llm-terminal .dot{width:10px;height:10px;border-radius:50%;display:inline-block}
.llm-terminal .dot.red{background:#ff5f56}.llm-terminal .dot.yellow{background:#ffbd2e}.llm-terminal .dot.green{background:#27c93f}
.llm-terminal .title{color:var(--muted);margin-left:6px;flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.llm-terminal__screen{padding:14px 16px;min-height:260px;white-space:pre-wrap;word-break:break-word}
.llm-terminal__prompt{border-top:1px dashed #30363d;padding:10px 16px;color:var(--muted)}
.llm-terminal .prompt{color:var(--accent);margin-right:6px}
.cursor{display:inline-block;width:10px;height:1.1em;background:var(--fg);vertical-align:-2px;margin-left:6px;animation:blink 1s steps(1) infinite}
@keyframes blink{0%,49%{opacity:1}50%,100%{opacity:0}}
.token-key{color:#a5d6ff}
.token-emph{color:#ffdf85}
.token-badge{background:#1f6feb;color:#fff;border-radius:10px;padding:0 6px;margin:0 2px;font-size:12px}
.link{color:var(--accent);text-decoration:none;border-bottom:1px dashed #30363d}
.link:hover{border-bottom-color:var(--accent)}
:root{color-scheme:dark}
</style>

<script>
(function(){
  const out = document.getElementById('llm-output');

  // 你可以在这里改打字速度（毫秒/字符）
  const SPEED_MS = 18;

  // 要显示的文本（会逐字打印）
  const content = [
    {h:"> system", c:"token-key"},
    "\nYou are an expert model tasked with summarizing ",
    {h:"Gang Jiang", c:"token-emph"},
    " (姜钢).\n\n",
    {h:"> user", c:"token-key"},
    "\nIntroduce yourself for a GitHub about page. Style: confident, research-oriented, minimal fluff, LLM token stream.\n\n",
    {h:"> assistant", c:"token-key"},
    "\n",
    // 下面是你的个人介绍正文（可随时编辑文案）
    "token_1  ",
    {h:"identity:", c:"token-key"},
    " PhD candidate @ University of Utah — graduating ",
    {h:"June 2026", c:"token-emph"},
    ". Open to ",
    {h:"AP track", c:"token-badge"},
    " ",
    {h:"PostDoc", c:"token-badge"},
    " ",
    {h:"Industry Research", c:"token-badge"},
    ".\n\n",

    "token_2  ",
    {h:"focus:", c:"token-key"},
    " AI & LLM for Buildings; Physics-informed modeling; (Urban) Building Energy Modeling & Calibration.\n",

    "token_3  ",
    {h:"now_building:", c:"token-key"},
    " ABEM — auto-building energy modeling with LLMs to boost accessibility & scalability.\n",

    "token_4  ",
    {h:"tooling:", c:"token-key"},
    " multi-agent flows, retrieval (RAG), 8760-h calibration, HPC pipelines.\n",

    "token_5  ",
    {h:"impact:", c:"token-key"},
    " lower modeling barriers; faster iteration; better-calibrated decisions.\n\n",

    "token_6  ",
    {h:"interests:", c:"token-key"},
    " building + urban energy, renewables integration, policy-aware analytics.\n",

    "token_7  ",
    {h:"links:", c:"token-key"},
    " homepage ",
    {a:"https://gangjiang1.github.io/", t:"gangjiang1.github.io"},
    " · scholar ",
    {a:"https://scholar.google.com/citations?user=RGjcgyEAAAAJ&hl=en", t:"Google Scholar"},
    " · project ",
    {a:"https://huggingface.co/EPlus-LLM", t:"EPlus-LLM"},
    ".\n\n",

    "token_8  ",
    {h:"contact:", c:"token-key"},
    " reach out for research collab, postdoc, or applied research roles.\n",
    "\n",
    {h:"✔ ready.", c:"token-emph"}
  ];

  // 把上面的结构转换为纯字符串+标注段，并逐字符打字
  let queue = [];
  for (const chunk of content) {
    if (typeof chunk === "string") {
      queue.push({type:"text", text:chunk});
    } else if (chunk.h) {
      queue.push({type:"span", cls:chunk.c || "", text:chunk.h});
    } else if (chunk.a) {
      queue.push({type:"link", href:chunk.a, text:chunk.t});
    } else {
      queue.push({type:"text", text:String(chunk)});
    }
  }

  function typeText(node, text, idx=0, done){
    if (idx >= text.length) { done && done(); return; }
    node.textContent += text[idx];
    setTimeout(()=>typeText(node, text, idx+1, done), SPEED_MS);
  }

  function appendSpan(text, cls, cb){
    const span = document.createElement('span');
    if (cls) span.className = cls;
    out.appendChild(span);
    typeText(span, text, 0, cb);
  }

  function appendLink(text, href, cb){
    const a = document.createElement('a');
    a.href = href; a.target = "_blank"; a.rel = "noopener"; a.className = "link";
    out.appendChild(a);
    typeText(a, text, 0, cb);
  }

  function appendPlain(text, cb){
    // 普通文本直接往输出容器里逐字打印
    const span = document.createElement('span');
    out.appendChild(span);
    typeText(span, text, 0, cb);
  }

  function run(i=0){
    if (i >= queue.length) return;
    const q = queue[i];
    const next = ()=> run(i+1);
    if (q.type === "span")      appendSpan(q.text, q.cls, next);
    else if (q.type === "link") appendLink(q.text, q.href, next);
    else                        appendPlain(q.text, next);
  }

  // 自动开始打字
  run();
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
