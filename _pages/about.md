---
permalink: /
title: "👋🏼 Hi there, I'm Gang!"
excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

<div class="llm-terminal">

  <div class="llm-terminal__bar">
    <span class="dot red"></span>
    <span class="dot yellow"></span>
    <span class="dot green"></span>
    <span class="title">Terminal</span>
  </div>

  <div class="llm-terminal__screen">

    <div class="chat-container">

      <div id="chat-messages" class="chat-messages">

        <div class="message assistant">
Hello! I’m Gang’s personal AI assistant.<br><br>

Gang is a fourth-year PhD candidate at The University of Utah and expects to graduate in July 2026.<br><br>

He is open to academic positions, including AP-track faculty roles, Postdoctoral positions, and industry research opportunities. Please feel free to reach out!<br><br>

His research interests include:<br>
• 🤖 AI & LLMs for Building Science and Automated Building Energy Modeling<br>
• ⚙️ Physics-Informed and Automated Modeling<br>
• 🏙 Urban Building Sustainability and Resilience<br><br>

Ask me anything about Gang:<br>
• 🙎🏻‍♂️ Background<br>
• 📍 Experience<br>
• 🔬 Research<br>
• 📄 Publications<br>
• 🏟️ The EPlus-LLM Platform
        </div>

      </div>

      <div class="chat-input-row">
        <span class="prompt-symbol">gang@home:~$</span>

        <input
          id="chat-input"
          type="text"
          placeholder="Ask my AI anything..."
          autocomplete="off"
        />

        <button id="send-btn">Send</button>
      </div>

    </div>

  </div>

</div>

<style>
.llm-terminal {
  --bg: #ffffff;
  --fg: #24292f;
  --muted: #6e7781;

  border: 1px solid #d0d7de;
  border-radius: 14px;
  background: var(--bg);
  color: var(--fg);
  font: 14px/1.7 ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
  box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  overflow: hidden;
  margin-top: 20px;
}

.llm-terminal__bar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 14px;
  background: #f6f8fa;
  border-bottom: 1px solid #d0d7de;
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
}

.red {
  background: #ff5f56;
}

.yellow {
  background: #ffbd2e;
}

.green {
  background: #27c93f;
}

.title {
  margin-left: 8px;
  color: #6e7781;
  font-weight: 600;
}

.llm-terminal__screen {
  padding: 18px;
  background: white;
}

.chat-container {
  border: 1px solid #d0d7de;
  border-radius: 12px;
  overflow: hidden;
  background: #ffffff;
}

.chat-messages {
  height: 420px;
  overflow-y: auto;
  padding: 18px;
  display: flex;
  flex-direction: column;
  gap: 14px;
  background: #fcfcfc;
}

.message {
  padding: 14px 16px;
  border-radius: 12px;
  white-space: normal;
  line-height: 1.7;
  max-width: 92%;
}

.message.user {
  align-self: flex-end;
  background: #eaf2ff;
  color: #0a3069;
  border: 1px solid #c6dbff;
}

.message.assistant {
  align-self: flex-start;
  background: #f6f8fa;
  color: #24292f;
  border: 1px solid #d0d7de;
}

.chat-input-row {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 14px 16px;
  border-top: 1px solid #d0d7de;
  background: #f6f8fa;
}

.prompt-symbol {
  color: #1a7f37;
  font-weight: 600;
  white-space: nowrap;
}

#chat-input {
  flex: 1;
  border: none;
  outline: none;
  background: transparent;
  font-family: inherit;
  font-size: 14px;
  color: #24292f;
}

#send-btn {
  border: 1px solid #d0d7de;
  background: white;
  border-radius: 8px;
  padding: 8px 16px;
  cursor: pointer;
  transition: 0.2s ease;
  font-family: inherit;
}

#send-btn:hover {
  background: #f3f4f6;
}

.chat-messages::-webkit-scrollbar {
  width: 8px;
}

.chat-messages::-webkit-scrollbar-thumb {
  background: #d0d7de;
  border-radius: 8px;
}

@media (max-width: 768px) {
  .chat-messages {
    height: 360px;
  }

  .message {
    max-width: 100%;
  }

  .chat-input-row {
    flex-wrap: wrap;
  }

  #send-btn {
    width: 100%;
  }
}
</style>

<script>
const OPENAI_API_KEY = "YOUR_NEW_OPENAI_API_KEY_HERE";

const input = document.getElementById("chat-input");
const button = document.getElementById("send-btn");
const messages = document.getElementById("chat-messages");

function appendMessage(role, text) {
  const div = document.createElement("div");
  div.className = `message ${role}`;
  div.textContent = text;
  messages.appendChild(div);
  messages.scrollTop = messages.scrollHeight;
  return div;
}

async function sendMessage() {
  const text = input.value.trim();

  if (!text) return;

  appendMessage("user", text);
  input.value = "";

  const aiDiv = appendMessage("assistant", "Thinking...");

  try {
    const response = await fetch(
      "https://api.openai.com/v1/chat/completions",
      {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          "Authorization": `Bearer ${OPENAI_API_KEY}`
        },
        body: JSON.stringify({
          model: "gpt-4o",
          temperature: 0,
          messages: [
            {
              role: "system",
              content: `
You are Gang Jiang's personal AI assistant.

You help visitors learn about Gang Jiang.

Gang Jiang is a fourth-year PhD candidate at The University of Utah, expecting to graduate in July 2026.

He is open to academic positions, including AP-track faculty roles, Postdoctoral positions, and industry research opportunities.

His research interests include:
- AI and LLMs for Building Science
- Automated Building Energy Modeling
- Physics-Informed and Automated Modeling
- Urban Building Sustainability and Resilience
- Building Simulation
- AI Agents for Building Science

He is developing automatic building energy modeling using large language models to improve modeling accessibility and scalability.

Projects include:
- EPlus-LLM
- ABEM
- Automated Energy Simulation
- LLM-driven Building Modeling

Publications include journals such as:
- Applied Energy
- Energy
- Energy and Buildings
- Automation in Construction

You should be professional, concise, technically strong, and friendly.

If users ask unrelated questions, politely redirect them toward Gang's research, publications, and professional background.
`
            },
            {
              role: "user",
              content: text
            }
          ]
        })
      }
    );

    const data = await response.json();

    if (data.error) {
      aiDiv.textContent = "OpenAI API Error: " + data.error.message;
      return;
    }

    aiDiv.textContent = data.choices[0].message.content;

  } catch (error) {
    console.error(error);
    aiDiv.textContent = "Error connecting to GPT-4o.";
  }
}

button.addEventListener("click", sendMessage);

input.addEventListener("keydown", function(e) {
  if (e.key === "Enter") {
    sendMessage();
  }
});
</script>

<h2>🖇 Open-Source Contributions</h2>

<div style="display:flex; align-items:flex-start; gap:24px; flex-wrap:wrap; margin-top:20px;">

  <!-- Left Column -->
  <div style="flex:1 1 300px; min-width:280px; line-height:1.8;">

    <a href="https://github.com/Gangjiang1/EPlus-LLM" target="_blank">
      <strong>EPlus-LLMv1/v2</strong>
    </a><br>

    LLM-driven automatic building energy modeling through natural language.<br><br>

    <a href="https://github.com/Gangjiang1/Prompting-for-Auto-building-Modeling" target="_blank">
      <strong>Prompting LLMs for ABEM</strong>
    </a><br>

    A comprehensive guideline for prompt engineering of LLMs in automated building energy modeling.

  </div>

  <!-- Right Column -->
  <div style="flex:0 0 420px; text-align:right;">

    <figure style="margin:0;">

      <img
        src="/images/graphic.png"
        alt="Illustration of LLM for Auto-building modeling."
        width="420"
        style="max-width:100%; height:auto; border-radius:10px;"
      >

      <figcaption style="font-size:14px; color:#666; margin-top:8px;">
        <em>Figure: LLM-Powered Auto-Building Modeling Workflow</em>
      </figcaption>

    </figure>

  </div>

</div>
﻿
## 🔬 Experience
🚀 Currently, I am collaborating with [Dr. Shandian Zhe](https://users.cs.utah.edu/~zhe/) (School of Computing, University of Utah) on NSF projects focused on improving LLMs' accuracy, computational efficiency, and robustness.
﻿
🧪 As part of my PhD journey, I am working with [Dr. Jianli Chen](https://scholar.google.com/citations?user=Y0ycryUAAAAJ&hl=en) on NSF-funded projects focused on Building Energy Modeling, Calibration, Optimization, and AI Applications in Buildings.
﻿
🧫 During my Master’s degree, at Tianjin University, I collaborated with [Dr. Zhe Tian](https://www.researchgate.net/profile/Zhe-Tian-2) on NSF-China projects related to Building Energy System Simulation and Building Fault Detection & Diagnosis.
﻿
✍️ I have completed internships at [Amazon AWS](https://aws.amazon.com/), where I have gained experience in designing and operating data centers with a focus on enhancing resilience and scalability, and at [SUNAC](https://www.sunac.com.cn/en/about.aspx), where I worked in real estate management.
﻿
## 🎉 News
🚀 My first-authored research paper, [Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling](https://doi.org/10.1016/j.energy.2025.134548), (*Energy, 2025*), has been recognized as a **🏆 Top 1% Highly Cited Paper** by ESI.
﻿
🚀 My first-authored research paper, [EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.123431), (*Applied Energy, 2024*), has also been selected as a **🏆 Top 1% Highly Cited Paper** and a **🔥 Top 0.1% Hot Cited Paper** by ESI.
﻿
📄 Dec. 2025 – First-authored paper, [Benchmarking Knowledge and Capability of Large Language Models in Building Science Domain](https://doi.org/10.59717/ipj.energy-use.2025.100026), has been published in *Energy Use*.
﻿
📢 Jun. 2025 – I will be attending the *ASHRAE Annual Conference* in Phoenix, Arizona. I am happy to engage in discussions and make connections!
﻿
📄 Apr. 2025 – The paper related to the [EPlus-LLMv2 platform](https://doi.org/10.1016/j.autcon.2025.106223), has been accepted for publication in *Automation in Construction*.
﻿
📄 Jan. 2025 – Our review paper, [A Review of Physics-Informed Machine Learning for Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.125169), has been published in *Applied Energy*.
﻿
📄 Jan. 2025 – My first-authored paper, [Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling](https://doi.org/10.1016/j.energy.2025.134548), has been published in *Energy*.
﻿
📄 Jun. 2024 – My first-authored paper, [A Deep Learning-Based Bayesian Framework for High-Resolution Calibration of Building Energy Models](https://doi.org/10.1016/j.enbuild.2024.114755), has been published in *Energy & Buildings*.
﻿
📄 May. 2024 – My first-authored paper, [EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling](https://doi.org/10.1016/j.apenergy.2024.123431), has been published in *Applied Energy*.
﻿
## 🗣️ Talks
🎤 Feb. 2026 – I’m excited to attend the *ASHRAE Winter Conference* in Las Vegas, NV! Looking forward to connecting with you there! 🌆  
I’ll be giving two presentations:  
(1) Large language models for automated building energy modeling (**Invited Talk**)  
(2) Real-world applications of the EPlus-LLM Platform (**Paper Session, Poster**)
﻿
🎤 Oct. 2025 – **Online talk** on BuildNext: Toward Automated Building Energy Modeling with Large Language Models [Slides](/files/Gang_LLM_ABEM_Slides.pdf)
﻿
🎤 Aug. 2025 – I was invited to give a talk at *ASHRAE CIDCO Conference* in Denver, CO! Topic: **Automating Building Energy Modeling from Natural Language**
﻿
🎤 Jun. 2024 – I will be speaking about [Natural Language Auto-Modeling via Fine-tuning LLMs](https://www.proquest.com/openview/390f54178cb137415c002b116d3ffe2c/1?pq-origsite=gscholar&cbl=34619) at the *ASHRAE Annual Conference* in Indianapolis, Indiana.

