---
permalink: /about/
title: "👋🏼 Hi there, I'm Gang!"
excerpt: "About me"
author_profile: true
layout: single
---

<!-- Optional image on the right -->
![LLM for Building Modeling](/images/graphic.png){: .align-right width="420px"}

<style>
#llm-typewriter {
  font-family: monospace;
  background-color: #0d1117;
  color: #d1d5da;
  padding: 16px;
  border-radius: 10px;
  font-size: 14px;
  white-space: pre-wrap;
  line-height: 1.6;
  min-height: 240px;
  position: relative;
  box-shadow: 0 0 10px #00000088;
  margin-top: 1.5rem;
}

.cursor {
  display: inline-block;
  width: 8px;
  height: 1em;
  background-color: #d1d5da;
  animation: blink 1s steps(1) infinite;
  vertical-align: bottom;
  margin-left: 2px;
}

@keyframes blink {
  0%, 50% { opacity: 1; }
  50.01%, 100% { opacity: 0; }
}
</style>

<div id="llm-typewriter"></div>

{% raw %}
<script>
const text = `
> token_1: 👋🏼 hello_world
> token_2: identify("Gang Jiang")
> token_3: role("PhD Candidate", university="University of Utah", year="2026")
> token_4: seeking(["AP track", "PostDoc", "Research (Industry)"])
> token_5: current_research := LLMs ⨉ Building Modeling
> token_6: goals := [accessibility, scalability, automation]
> token_7: interests += [🤖 AI_for_Buildings, ⚙️ Physics_Informed_Models, 🏙 Urban_BEM_and_Calibration]
> token_8: message("Feel free to connect!")
`;

const container = document.getElementById("llm-typewriter");
const cursor = document.createElement("span");
cursor.classList.add("cursor");
container.appendChild(cursor);

let i = 0;

function type() {
  if (i < text.length) {
    const char = text[i];
    cursor.insertAdjacentText("beforebegin", char);
    i++;
    setTimeout(type, char === "\n" ? 200 : 20); // slower on newline
  }
}

window.onload = () => setTimeout(type, 400);
</script>
{% endraw %}

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
