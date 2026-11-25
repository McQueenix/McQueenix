# Hi, I'm Guruprasad VM 👋

**GenAI & Python backend engineer** · I build LLM-powered tools that real teams use every week: RAG pipelines, AI review automation and FastAPI services that hold up in production.

- 🧠 ~4 years of software engineering, focused since 2024 on **GenAI, LLM engineering and RAG**
- 🏢 I build enterprise AI and automation tools for **Japanese clients**, from prototype through production rollout
- 🏆 Lead author of a research whitepaper on adaptive LLM routing that won a **Good Paper Award** and a **Bronze Star** (2026)
- 📍 India · open to roles in Bengaluru, remote, or overseas
- 📫 **guruprasad30122000@gmail.com**

---

## 🚀 Featured projects

### [Countersign](https://github.com/McQueenix/countersign) — a trust layer between AI agents and PayPal
*Built for the PayPal AI Hackathon (2026)*

AI agents are starting to move money, and they read inboxes full of text written by strangers. In Countersign the agent **never holds payment credentials**. Every payout, invoice or purchase it asks for passes through three gates before it reaches PayPal:

1. **Policy engine.** Plain code enforces the owner's written mandate as hard limits.
2. **Independent AI risk review.** A second model reads the source record and looks for social engineering.
3. **Signed decision.** Each outcome gets an Ed25519-signed proof that anyone can verify, and its link travels inside the PayPal payment.

`Python` `FastAPI` `PayPal REST (Payouts, Invoicing v2, Orders v2)` `Gemini / OpenAI-compatible LLMs` `Ed25519` `Model Context Protocol` · **116 tests**

### [speech-to-text](https://github.com/McQueenix/speech-to-text) — real-time Hindi + English transcription
Speak in Hindi, English or a mix of both ("Kal meeting hai, please send the report") and the words appear as you talk.

- The browser captures audio in an **AudioWorklet**, downsamples it to 16 kHz PCM and streams it over a **WebSocket** to FastAPI, which forwards it to the **Gemini Live API**
- Transcripts are saved to **PostgreSQL** and shown in a dashboard with search, full CRUD and text-to-speech playback
- The speech engine sits behind a small interface, so a self-hosted model can replace it without touching the rest of the app

`FastAPI` `WebSockets` `PostgreSQL` `SQLAlchemy 2` `Gemini Live API` · one-click Render deploy · tested with a fake speech engine

### [pymend](https://github.com/McQueenix/pymend) — offline Python bug finder & safe auto-fixer
Zero dependencies, so it runs on locked-down machines where you can't `pip install` much.

- A single AST walk runs **14 bug-pattern rules**
- **6 of them auto-fix**, but only when the fix can't change behaviour. Each edit is exact and byte-positioned, the file is re-parsed afterwards, and if the result wouldn't compile every edit is rolled back
- Works as a CLI, a CI gate (`--check`) and a pre-commit hook, with JSON and diff output

`Python stdlib` `ast` `CLI` `pytest` `GitHub Actions`

---

## 🛠️ How I build things

Every repo here follows the same walkthrough. Open any of them and you'll find these steps:

| Step | What I do | Where to see it |
|---|---|---|
| **1. Start from the failure mode** | Write down what goes wrong today before writing code | Countersign → *The problem* |
| **2. Keep the AI behind an interface** | LLMs and speech engines sit behind small, swappable boundaries, so they can be tested and replaced | speech-to-text → `app/live.py` (`Transcriber`) |
| **3. Put hard rules in plain code** | Limits and safety checks are deterministic code; the model explains and reviews, it doesn't enforce | Countersign → policy engine |
| **4. Add a safety net to anything automatic** | Changes are verified before they're kept, and rolled back if they fail | pymend → re-parse after every fix |
| **5. Test with fakes, not luck** | External APIs get fake implementations, so the whole flow runs in CI with no keys | speech-to-text → `tests/test_live.py` |
| **6. Make it run for the next person** | README first, `.env.example`, one-command setup, deploy blueprint | every repo |

---

## 💼 Professional work

*Details are kept general because these systems belong to my clients.*

- **AI inspection pipeline.** A FastAPI dashboard that validates Japanese Excel inspection workbooks through rule-based L1/L2 checks and an LLM-based L3 review, then writes the verdicts back into the workbook. It re-checks only rows that changed, using hash-based row diffing over LanceDB snapshots, and ships as a packaged desktop build.
- **LLM review automation.** A Flask tool that turns a weekly manual judgement process into an LLM-assisted run, with versioned prompts tracking the client's rule changes.
- **AI-vs-human evaluation.** Ground-truth tooling that measures model verdicts against human reviewers, with F1 targets above 90%.
- **Hybrid RAG for investigations.** FAISS and BM25 retrieval over internal knowledge, combined with Azure OpenAI and HuggingFace embeddings.
- **Performance.** A vectorization optimization in FAISS that cut processing time by about **39%**.

---

## 🧰 Tech stack

- **AI / LLM:** RAG · prompt engineering · LangChain / LangGraph · Model Context Protocol · Azure OpenAI · Gemini · FAISS · LanceDB · BM25 · HuggingFace embeddings · XGBoost
- **Backend:** Python · FastAPI · Flask · WebSockets · SQLAlchemy · REST API design · pytest
- **Data & tools:** PostgreSQL · SQLite · openpyxl / Excel automation · PyInstaller · Git · Azure DevOps · GitHub Actions
- **Earlier:** Java · Spring Boot

---

## 📜 Recognition & certifications

- **Good Paper Award** and **Bronze Star**, as lead author of a whitepaper on contextual-bandit LLM routing, conformal hallucination calibration and drift-aware feedback (2026)
- **AI & DDM Award 2025** – Practical Case Competition
- Microsoft Azure Fundamentals (**AZ-900**)
- Google AI certification
- Career Essentials in Generative AI (Microsoft & LinkedIn)
- Ethics in the Age of Generative AI (LinkedIn Learning)
- Clean Code (Udemy)

---

## 📫 Get in touch

Email is the best way to reach me: **guruprasad30122000@gmail.com**. I'm happy to talk about GenAI engineering roles, LLM tooling or any of the projects above.
