# 🧛 DRACULA (Direct Response & Automated Customer Utility Language Architecture)

> **Developed by:** Ibrahim El Feqi (hema1122441)
> **License:** MIT
> **Core Stack:** Python 3.10+ | FastAPI | Ollama (Local SLM Inference) | Meta Webhook API

---

## 🌍 Language / اللغة
* [English (#english)](#english)
* [العربية (#arabic)](#arabic)

---

<a name="english"></a>
## 🇺🇸 English Version

DRACULA is an enterprise-grade digital sales automation engine designed to run 100% locally. By utilizing the official Meta Webhook Architecture, it interfaces directly with Facebook Messenger, Instagram DMs, and WhatsApp Cloud API, delivering microsecond responses while maintaining absolute data sovereignty.

### 🎯 Engineering Philosophy
* **Plugging the Silent Revenue Leak:** E-commerce conversion rates decay by over 60% if response times exceed 5 minutes. DRACULA responds instantly.
* **Leak-Proof Architecture:** Completely eliminates brittle browser extensions and DOM scraping configurations that bloat memory and trigger account bans.
* **Resource Optimization:** Tailored to deliver high-throughput local inference on developer hardware (optimized for Core i5 and 8GB RAM environments) by isolating memory exclusively for Small Language Models (SLMs).

### 🛠 Technical Architecture

[ Client: FB / IG / WA ]
│
▼  (Meta Official Webhook - HTTP POST JSON)
[ Secure Tunnel / Ngrok ]
│
▼
[ DRACULA Engine (FastAPI Async) ]
│
├─► 1. Cleans payload & enforces strict Thread-ID isolation (No session leaks).
├─► 2. Sliding window memory truncation (Keeps only last 4 messages to prevent hallucination).
└─► 3. Forwards structured context via Native Local HTTP API.
│
▼
[ Local Ollama Core ] ◄──► [ SLM Model: qwen2.5-coder:1.5b ]


### 🧠 Core Features
* **Unified Omnichannel Router:** A single asynchronous endpoint that decodes payloads from multiple Meta platforms seamlessly.
* **Deterministic Constraints:** Models are bound by strict temperature limits (`Temperature = 0.3`) to prevent algorithmic hallucination and force alignment with local product inventories.
* **High-Fidelity Conversational Engine:** Crafted to output sharp, high-converting Egyptian Arabic prose, steering the user strictly toward dropping their contact details to close the deal.

### 🚀 Quick Start
1. **Pull the Local Model:**
   ```bash
   ollama pull qwen2.5-coder:1.5b

    Install Dependencies:
    Bash

    pip install fastapi uvicorn httpx

    Expose Port 8000 via Secure Tunnel:
    Bash

    ngrok http 8000

    Run the Engine:
    Bash

    python main.py
