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

  <!-- Terminal Top Bar -->
  <div class="llm-terminal__bar">
    <span class="dot red"></span>
    <span class="dot yellow"></span>
    <span class="dot green"></span>
    <span class="title">Gang AI Terminal</span>
  </div>

  <!-- Intro Screen -->
  <div class="llm-terminal__screen">

    <div class="type-line"
         style="--n:94; --dur:calc(var(--n)*0.035s); --delay:0.6s;">
      👨🏻‍💻 I'm a fourth-year PhD candidate at The University of Utah, expecting to graduate in
    </div>

    <div class="type-line"
         style="--n:12; --dur:calc(var(--n)*0.035s); --delay:4.2s;">
      June 2026.
    </div>

    <div class="type-line"
         style="--n:81; --dur:calc(var(--n)*0.035s); --delay:5.0s;">
      I am open to work, including AP track, PostDoc, and industry research positions.
    </div>

    <div class="type-line"
         style="--n:31; --dur:calc(var(--n)*0.035s); --delay:8.0s;">
      Please feel free to reach out!
    </div>

    <div class="type-line"
         style="--n:26; --dur:calc(var(--n)*0.035s); --delay:9.0s;">
      📍 My research interests:
    </div>

    <div class="type-line"
         style="--n:40; --dur:calc(var(--n)*0.035s); --delay:10.0s;">
      - 🤖 AI & LLM for Building Science
    </div>

    <div class="type-line"
         style="--n:45; --dur:calc(var(--n)*0.035s); --delay:11.5s;">
      - ⚙️ Physics-Informed & Automated Modeling
    </div>

    <div class="type-line"
         style="--n:58; --dur:calc(var(--n)*0.035s); --delay:13.3s;">
      - 🏙 Urban Building Sustainability & Resilience
    </div>

    <div class="type-line"
         style="--n:88; --dur:calc(var(--n)*0.035s); --delay:15.0s;">
      📌 I'm developing auto-building energy modeling using large language models.
    </div>

    <div class="type-line"
         style="--n:71; --dur:calc(var(--n)*0.035s); --delay:18.0s;">
      LLMs improve building modeling accessibility and scalability.
    </div>

  </div>

  <!-- Chat Window -->
  <div class="chat-container">

    <div id="chat-messages" class="chat-messages">

      <div class="message assistant">
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

      <span class="prompt-symbol">
gang@home:~$
      </span>

      <input
        id="chat-input"
        type="text"
        placeholder="Ask my AI anything..."
        autocomplete="off"
      />

      <button id="send-btn">
Send
      </button>

    </div>

  </div>

</div>

<style>

/* -------------------- Terminal UI -------------------- */

.llm-terminal {

  --bg: #ffffff;
  --fg: #24292f;
  --muted: #6e7781;

  border: 1px solid #d0d7de;
  border-radius: 14px;
  background: var(--bg);
  color: var(--fg);

  font: 14px/1.7
        ui-monospace,
        SFMono-Regular,
        Menlo,
        Monaco,
        Consolas,
        monospace;

  box-shadow:
    0 10px 30px rgba(0,0,0,0.08);

  overflow: hidden;

  margin-top: 20px;
}

/* -------------------- Top Bar -------------------- */

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

/* -------------------- Intro Screen -------------------- */

.llm-terminal__screen {

  padding: 18px;

  border-bottom: 1px dashed #d0d7de;

  min-height: 320px;
}

/* -------------------- Typewriter -------------------- */

.type-line {

  position: relative;

  display: block;

  white-space: pre-wrap;

  overflow: hidden;

  width: 0ch;

  border-right: 2px solid #57606a;

  animation:
    typing var(--dur) steps(var(--n)) forwards,
    caret var(--dur) steps(1) forwards;

  animation-delay:
    var(--delay),
    var(--delay);
}

@keyframes typing {

  from {
    width: 0ch;
  }

  to {
    width: calc(var(--n) * 1ch);
  }
}

@keyframes caret {

  0%, 49% {
    border-right-color: #24292f;
  }

  50%, 100% {
    border-right-color: transparent;
  }
}

/* -------------------- Chat Container -------------------- */

.chat-container {

  background: #ffffff;
}

/* -------------------- Chat Messages -------------------- */

.chat-messages {

  height: 420px;

  overflow-y: auto;

  padding: 20px;

  display: flex;

  flex-direction: column;

  gap: 16px;

  background: #fcfcfc;
}

/* -------------------- Messages -------------------- */

.message {

  padding: 14px 16px;

  border-radius: 12px;

  white-space: pre-wrap;

  line-height: 1.7;

  max-width: 90%;
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

/* -------------------- Input Row -------------------- */

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

/* -------------------- Input -------------------- */

#chat-input {

  flex: 1;

  border: none;

  outline: none;

  background: transparent;

  font-family: inherit;

  font-size: 14px;

  color: #24292f;
}

/* -------------------- Button -------------------- */

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

/* -------------------- Scrollbar -------------------- */

.chat-messages::-webkit-scrollbar {

  width: 8px;
}

.chat-messages::-webkit-scrollbar-thumb {

  background: #d0d7de;

  border-radius: 8px;
}

/* -------------------- Mobile -------------------- */

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

/* =========================================================
   IMPORTANT:
   Replace with your own OpenAI API Key
========================================================= */

const OPENAI_API_KEY = "YOUR_OPENAI_API_KEY";

/* =========================================================
   DOM
========================================================= */

const input =
  document.getElementById("chat-input");

const button =
  document.getElementById("send-btn");

const messages =
  document.getElementById("chat-messages");

/* =========================================================
   Add Message
========================================================= */

function appendMessage(role, text) {

  const div = document.createElement("div");

  div.className = `message ${role}`;

  div.textContent = text;

  messages.appendChild(div);

  messages.scrollTop =
    messages.scrollHeight;

  return div;
}

/* =========================================================
   GPT Request
========================================================= */

async function sendMessage() {

  const text = input.value.trim();

  if (!text) return;

  appendMessage(
    "user",
    text
  );

  input.value = "";

  const aiDiv = appendMessage(
    "assistant",
    "Thinking..."
  );

  try {

    const response = await fetch(
      "https://api.openai.com/v1/chat/completions",
      {

        method: "POST",

        headers: {

          "Content-Type":
            "application/json",

          "Authorization":
            `Bearer ${OPENAI_API_KEY}`
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

- Gang's research
- Publications
- EPlus-LLM
- Automated Building Energy Modeling
- Building Science
- AI for Sustainability
- Urban Sustainability
- Collaborations
- Research Experience
- Professional Background

Background:

Gang Jiang is a PhD candidate
at the University of Utah.

Research interests include:

- AI & LLM for Building Science
- Automated Building Energy Modeling
- Physics-informed AI
- Urban Sustainability
- Building Simulation
- Energy Modeling
- AI Agents

Projects include:

- EPlus-LLM
- ABEM
- Automated Energy Simulation
- LLM-driven Modeling

Published in journals such as:

- Applied Energy
- Energy
- Energy & Buildings
- Automation in Construction

You should be:

- professional
- concise
- friendly
- technically strong

If users ask unrelated questions,
politely redirect the conversation
toward Gang's expertise and work.
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

    const data =
      await response.json();

    aiDiv.textContent =
      data.choices[0].message.content;

  } catch (error) {

    console.error(error);

    aiDiv.textContent =
      "Error connecting to GPT-4o.";
  }
}

/* =========================================================
   Events
========================================================= */

button.addEventListener(
  "click",
  sendMessage
);

input.addEventListener(
  "keydown",
  (e) => {

    if (e.key === "Enter") {

      sendMessage();
    }
  }
);

</script>
