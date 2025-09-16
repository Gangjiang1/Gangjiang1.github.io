---
permalink: /
title: "👋🏼 Hi there, I'm Gang!"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<style>
.terminal {
  background-color: #1e1e1e;
  color: #f0f0f0;
  font-family: 'Courier New', monospace;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
  white-space: pre-wrap;
  overflow: hidden;
  line-height: 1.6;
  max-width: 800px;
  margin: 0 auto 2rem;
  position: relative;
}

.terminal::before {
  content: "gang@llm-terminal ~ $";
  color: #4ade80;
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

.cursor {
  display: inline-block;
  width: 8px;
  height: 1.2em;
  background-color: #f0f0f0;
  animation: blink 1s step-end infinite;
  vertical-align: text-bottom;
  margin-left: 2px;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}

.token-tag {
  color: #a0a0a0;
  font-size: 0.85em;
  opacity: 0.7;
}
</style>

<div class="terminal" id="terminal-output">
<span class="token-tag">[system] initializing LLM persona...</span>
<br><br>
</div>

<script>
const fullText = `Hi, I'm Gang. Third-year PhD candidate at The University of Utah, researching at the intersection of AI & physics-informed building modeling. Open to collaboration.`;

const terminal = document.getElementById('terminal-output');
const typingDelay = 50; // 每个字符间隔（毫秒），可调快慢
let i = 0;

function typeWriter() {
  if (i < fullText.length) {
    const char = fullText.charAt(i);
    // 处理换行
    if (char === '\\n') {
      terminal.innerHTML += '<br>';
    } else {
      terminal.innerHTML += char;
    }
    i++;
    setTimeout(typeWriter, typingDelay);
  } else {
    // 打字完成后添加光标
    terminal.innerHTML += ' <span class="cursor"></span>';
  }
}

// 延迟 500ms 后开始打字，模拟“模型思考中”
setTimeout(typeWriter, 500);
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
