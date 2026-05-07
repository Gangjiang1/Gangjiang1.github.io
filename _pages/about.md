---
permalink: /
title: "👋🏼 Hi there, I'm Gang, a PhD candidate at The University of Utah!"
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
    <span class="title">Gang AI Assistant</span>
  </div>

  <div class="llm-terminal__screen">

    <div class="chat-container">

      <div id="chat-messages" class="chat-messages">

        <div class="message assistant">
Hello! I’m Gang’s personal AI assistant!<br><br>
Gang's research interests include:<br>
  • 👾 AI & LLMs for Building Science and Automated Building Energy Modeling<br>
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
        <span class="prompt-symbol">🤖</span>

        <input
          id="chat-input"
          type="text"
          placeholder="Ask anything..."
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
  margin-bottom: 36px;
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
  flex-shrink: 0;
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
  white-space: pre-wrap;
  word-break: break-word;
  overflow-wrap: anywhere;
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
  min-width: 0;
  border: none;
  outline: none;
  background: transparent;
  font-family: inherit;
  font-size: 14px;
  color: #24292f;
}

#chat-input::placeholder {
  color: #8c959f;
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

#send-btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.chat-messages::-webkit-scrollbar {
  width: 8px;
}

.chat-messages::-webkit-scrollbar-thumb {
  background: #d0d7de;
  border-radius: 8px;
}

.home-section {
  margin-top: 36px;
  margin-bottom: 36px;
}

.home-section p {
  line-height: 1.8;
}

.contribution-wrapper {
  display: flex;
  align-items: flex-start;
  gap: 24px;
  flex-wrap: wrap;
  margin-top: 20px;
}

.contribution-text {
  flex: 1 1 300px;
  min-width: 280px;
  line-height: 1.8;
}

.contribution-figure {
  flex: 0 0 420px;
  text-align: right;
}

.contribution-figure img {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
}

.contribution-figure figcaption {
  font-size: 14px;
  color: #666;
  margin-top: 8px;
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

  .contribution-figure {
    flex: 1 1 100%;
    text-align: center;
  }
}
</style>

<script>
const OPENROUTER_API_KEY = "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";

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

function getConversationHistory() {
  const messageDivs = messages.querySelectorAll(".message");
  const history = [];

  messageDivs.forEach(div => {
    const role = div.classList.contains("user") ? "user" : "assistant";
    const content = div.textContent.trim();

    if (content && content !== "Thinking...") {
      history.push({ role, content });
    }
  });

  return history.slice(-8);
}

async function sendMessage() {
  const text = input.value.trim();

  if (!text) return;

  appendMessage("user", text);
  input.value = "";
  input.focus();

  const aiDiv = appendMessage("assistant", "Thinking...");
  button.disabled = true;

  try {
    const conversationHistory = getConversationHistory();

    const response = await fetch(
      "https://openrouter.ai/api/v1/chat/completions",
      {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
          "Authorization": `Bearer ${OPENROUTER_API_KEY}`,
          "HTTP-Referer": "https://yourwebsite.com",
          "X-Title": "Gang AI Assistant"
        },
        body: JSON.stringify({
          model: "openai/gpt-4o-mini",
          temperature: 0.2,
          messages: [
            {
              role: "system",
              content: `
You are Gang Jiang's personal AI assistant on his academic website.

Your job is to help visitors learn about Gang Jiang in a professional, concise, and friendly way.

Basic profile:
Gang Jiang is a fourth-year PhD candidate at The University of Utah. He expects to graduate in July 2026.
He is open to academic positions, including AP-track faculty roles, postdoctoral positions, and industry research opportunities.

Research interests:
1. AI and large language models for building science.
2. Automated Building Energy Modeling.
3. Physics-informed and automated modeling.
4. Urban building sustainability and resilience.

Research and platforms:
Gang develops EPlus-LLM and EPlus-LLMv2, large language model-based platforms for automated building energy modeling.
His work focuses on making building energy modeling more accessible, scalable, and automated through LLMs, multimodal reasoning, prompt engineering, fine-tuning, and agentic AI systems.

Open-source projects:
1. EPlus-LLMv1/v2: LLM-driven automatic building energy modeling through natural language.
2. Prompting LLMs for ABEM: A guideline for prompt engineering of LLMs in automated building energy modeling.

Selected publications:
1. EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling, Applied Energy, 2024.
2. Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling, Energy, 2025.
3. A Deep Learning-Based Bayesian Framework for High-Resolution Calibration of Building Energy Models, Energy & Buildings, 2024.
4. A Review of Physics-Informed Machine Learning for Building Energy Modeling, Applied Energy, 2025.
5. EPlus-LLMv2 platform paper, Automation in Construction, 2025.
6. Benchmarking Knowledge and Capability of Large Language Models in Building Science Domain, Energy Use, 2025.

Experience:
Gang has collaborated with Dr. Shandian Zhe at the School of Computing, University of Utah, on NSF projects related to LLM accuracy, computational efficiency, and robustness.
He works with Dr. Jianli Chen on NSF-funded projects related to Building Energy Modeling, Calibration, Optimization, and AI applications in buildings.
During his Master's degree at Tianjin University, he collaborated with Dr. Zhe Tian on NSF-China projects related to Building Energy System Simulation and Fault Detection & Diagnosis.
He also completed internships at Amazon AWS and SUNAC.

Talks:
Gang has given or will give talks at ASHRAE conferences and BuildNext on automated building energy modeling with large language models.

Answering style:
Use clear and concise answers.
If visitors ask about Gang's research, explain it in an accessible way.
If visitors ask about publications, summarize the most relevant papers.
If visitors ask about job opportunities or collaboration, encourage them to contact Gang.
Do not make up information that is not provided.
              `
            },
            ...conversationHistory,
            {
              role: "user",
              content: text
            }
          ]
        })
      }
    );

    const data = await response.json();

    if (!response.ok) {
      aiDiv.textContent = "API Error: " + (data.error?.message || "Request failed.");
      return;
    }

    if (data.error) {
      aiDiv.textContent = "API Error: " + data.error.message;
      return;
    }

    const reply = data.choices?.[0]?.message?.content;

    if (!reply) {
      aiDiv.textContent = "Sorry, I did not receive a valid response.";
      return;
    }

    aiDiv.textContent = reply;

  } catch (error) {
    console.error(error);
    aiDiv.textContent = "Error connecting to the AI assistant. Please try again later.";
  } finally {
    button.disabled = false;
  }
}

button.addEventListener("click", sendMessage);

input.addEventListener("keydown", function(e) {
  if (e.key === "Enter") {
    sendMessage();
  }
});
</script>

<div class="home-section">

<h2>🖇 Open-Source Contributions</h2>

<div class="contribution-wrapper">

  <div class="contribution-text">

    <a href="https://github.com/Gangjiang1/EPlus-LLM" target="_blank">
      <strong>EPlus-LLMv1/v2</strong>
    </a><br>

    LLM-driven automatic building energy modeling through natural language.<br><br>

    <a href="https://github.com/Gangjiang1/Prompting-for-Auto-building-Modeling" target="_blank">
      <strong>Prompting LLMs for ABEM</strong>
    </a><br>

    A comprehensive guideline for prompt engineering of LLMs in automated building energy modeling.

  </div>

  <div class="contribution-figure">

    <figure style="margin:0;">

      <img
        src="/images/graphic.png"
        alt="Illustration of LLM for automated building modeling."
        width="420"
      >

      <figcaption>
        <em>Figure: LLM-Powered Auto-Building Modeling Workflow</em>
      </figcaption>

    </figure>

  </div>

</div>

</div>

<div class="home-section">

<h2>🔬 Experience</h2>

<p>
🚀 Currently, I am collaborating with 
<a href="https://users.cs.utah.edu/~zhe/" target="_blank">Dr. Shandian Zhe</a>
from the School of Computing at the University of Utah on NSF projects focused on improving LLMs' accuracy, computational efficiency, and robustness.
</p>

<p>
🧪 As part of my PhD journey, I am working with
<a href="https://scholar.google.com/citations?user=Y0ycryUAAAAJ&hl=en" target="_blank">Dr. Jianli Chen</a>
on NSF-funded projects focused on Building Energy Modeling, Calibration, Optimization, and AI Applications in Buildings.
</p>

<p>
🧫 During my Master’s degree at Tianjin University, I collaborated with
<a href="https://www.researchgate.net/profile/Zhe-Tian-2" target="_blank">Dr. Zhe Tian</a>
on NSF-China projects related to Building Energy System Simulation and Building Fault Detection and Diagnosis.
</p>

<p>
✍️ I completed internships at
<a href="https://aws.amazon.com/" target="_blank">Amazon AWS</a>,
where I gained experience in designing and operating data centers with a focus on resilience and scalability, and at
<a href="https://www.sunac.com.cn/en/about.aspx" target="_blank">SUNAC</a>,
where I worked in real estate management.
</p>

</div>

<div class="home-section">

<h2>🎉 News</h2>

<p>
🚀 My first-authored research paper,
<a href="https://doi.org/10.1016/j.energy.2025.134548" target="_blank">
Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling
</a>,
<em>Energy, 2025</em>, has been recognized as a
<strong>🏆 Top 1% Highly Cited Paper</strong> by ESI.
</p>

<p>
🚀 My first-authored research paper,
<a href="https://doi.org/10.1016/j.apenergy.2024.123431" target="_blank">
EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling
</a>,
<em>Applied Energy, 2024</em>, has also been selected as a
<strong>🏆 Top 1% Highly Cited Paper</strong> and a
<strong>🔥 Top 0.1% Hot Cited Paper</strong> by ESI.
</p>

<p>
📄 Dec. 2025 – First-authored paper,
<a href="https://doi.org/10.59717/ipj.energy-use.2025.100026" target="_blank">
Benchmarking Knowledge and Capability of Large Language Models in Building Science Domain
</a>,
has been published in <em>Energy Use</em>.
</p>

<p>
📢 Jun. 2025 – I will be attending the <em>ASHRAE Annual Conference</em> in Phoenix, Arizona. I am happy to engage in discussions and make connections!
</p>

<p>
📄 Apr. 2025 – The paper related to the
<a href="https://doi.org/10.1016/j.autcon.2025.106223" target="_blank">EPlus-LLMv2 platform</a>
has been accepted for publication in <em>Automation in Construction</em>.
</p>

<p>
📄 Jan. 2025 – Our review paper,
<a href="https://doi.org/10.1016/j.apenergy.2024.125169" target="_blank">
A Review of Physics-Informed Machine Learning for Building Energy Modeling
</a>,
has been published in <em>Applied Energy</em>.
</p>

<p>
📄 Jan. 2025 – My first-authored paper,
<a href="https://doi.org/10.1016/j.energy.2025.134548" target="_blank">
Prompt Engineering to Inform Large Language Models in Automated Building Energy Modeling
</a>,
has been published in <em>Energy</em>.
</p>

<p>
📄 Jun. 2024 – My first-authored paper,
<a href="https://doi.org/10.1016/j.enbuild.2024.114755" target="_blank">
A Deep Learning-Based Bayesian Framework for High-Resolution Calibration of Building Energy Models
</a>,
has been published in <em>Energy & Buildings</em>.
</p>

<p>
📄 May. 2024 – My first-authored paper,
<a href="https://doi.org/10.1016/j.apenergy.2024.123431" target="_blank">
EPlus-LLM: A Large Language Model-Based Computing Platform for Automated Building Energy Modeling
</a>,
has been published in <em>Applied Energy</em>.
</p>

</div>

<div class="home-section">

<h2>🗣️ Talks</h2>

<p>
🎤 Feb. 2026 – I’m excited to attend the <em>ASHRAE Winter Conference</em> in Las Vegas, NV! Looking forward to connecting with you there! 🌆<br>
I’ll be giving two presentations:<br>
(1) Large language models for automated building energy modeling <strong>(Invited Talk)</strong><br>
(2) Real-world applications of the EPlus-LLM Platform <strong>(Paper Session, Poster)</strong>
</p>

<p>
🎤 Oct. 2025 – <strong>Online talk</strong> on BuildNext:
Toward Automated Building Energy Modeling with Large Language Models
<a href="/files/Gang_LLM_ABEM_Slides.pdf">[Slides]</a>
</p>

<p>
🎤 Aug. 2025 – I was invited to give a talk at <em>ASHRAE CIDCO Conference</em> in Denver, CO! Topic:
<strong>Automating Building Energy Modeling from Natural Language</strong>
</p>

<p>
🎤 Jun. 2024 – I will be speaking about
<a href="https://www.proquest.com/openview/390f54178cb137415c002b116d3ffe2c/1?pq-origsite=gscholar&cbl=34619" target="_blank">
Natural Language Auto-Modeling via Fine-tuning LLMs
</a>
at the <em>ASHRAE Annual Conference</em> in Indianapolis, Indiana.
</p>

</div>
