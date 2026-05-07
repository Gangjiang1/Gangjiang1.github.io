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
    <span class="title">Gang AI Terminal</span>
  </div>

  <div class="llm-terminal__screen">

    <div class="chat-container">

      <div id="chat-messages" class="chat-messages">

        <div class="message assistant">
👨🏻‍💻 I'm a fourth-year PhD candidate at The University of Utah, expecting to graduate in June 2026.

I am open to work, including AP track, PostDoc, and industry research positions.

Please feel free to reach out!

📍 My research interests:
- 🤖 AI & LLM for Building Science
- ⚙️ Physics-Informed & Automated Modeling
- 🏙 Urban Building Sustainability & Resilience

📌 I'm developing auto-building energy modeling using large language models.

LLMs improve building modeling accessibility and scalability.

Hello! I'm Gang AI 🤖

Ask me anything about:
• Research
• Publications
• EPlus-LLM
• ABEM
• Building Science
• AI for Sustainability
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
  white-space: pre-wrap;
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
const OPENAI_API_KEY = "YOUR_OPENAI_API_KEY";

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
          temperature: 0.7,
          messages: [
            {
              role: "system",
              content: `
You are Gang Jiang's personal AI assistant.

You help visitors learn about:

- Research
- Publications
- EPlus-LLM
- ABEM
- Building Science
- AI for Sustainability
- Collaborations
- Professional Experience

Background:

Gang Jiang is a fourth-year PhD candidate at The University of Utah, expecting to graduate in June 2026.

He is open to work, including AP track, PostDoc, and industry research positions.

His research interests include:

- AI & LLM for Building Science
- Physics-Informed & Automated Modeling
- Urban Building Sustainability & Resilience
- Automated Building Energy Modeling
- Building Simulation
- AI Agents for Building Science

He is developing auto-building energy modeling using large language models to improve modeling accessibility and scalability.

Projects include:

- EPlus-LLM
- ABEM
- Automated Energy Simulation
- LLM-driven Building Modeling

Publications include journals such as:

- Applied Energy
- Energy
- Energy & Buildings
- Automation in Construction

You should be:

- professional
- concise
- technically strong
- friendly

If users ask unrelated questions, politely redirect toward Gang's research, publications, and professional background.
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
