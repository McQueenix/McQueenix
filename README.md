# Hi, I'm Guruprasad V M 👋

**Software engineer · Generative AI & Python backend** — I build production-grade GenAI systems, RAG pipelines and Python REST services for global enterprise clients, with a focus on reliable, cost-efficient LLM engineering.

- 🧠 **4+ years** of experience; my recent work is multi-step / agentic LLM pipelines, evaluation against real client data, and AI tools that non-technical users can run
- 🏢 **Fujitsu** (Jan 2024 – present) · all projects delivered for Japanese enterprise clients
- 🏆 **Platinum Award** (Fujitsu India GDC, 2026) · **Good Paper Award** (Fujitsu Convention 2026) · Silver & Bronze project-excellence awards
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

## 💼 Experience

### Fujitsu — Associate Technical Service Engineer (Software Engineer, Generative AI & Backend)
*Jan 2024 – present · all projects delivered for Japanese clients*

**Operational Efficiency Tool & Enterprise AI Platform** (Jun 2025 – present)
- **Enterprise AI inspection-validation platform.** A FastAPI dashboard and backend that validates complex Japanese-language inspection spreadsheets (.xlsm) through a multi-layer engine: deterministic rule checks plus LLM-powered evaluation. It replaced slow, error-prone manual review.
- **Multi-phase LLM evaluation pipeline.** Structured-output enforcement, a five-stage JSON-repair cascade, retry and relaxation logic, and global timeouts, which made it far more reliable under concurrent load.
- **RAG with graceful degradation.** A RAG layer over LanceDB with a three-tier fallback (RAG → direct LLM → rule-based), so the system always returns a usable answer.
- **Incremental evaluation engine.** Hash-based routing sends only new or changed rows through the LLM, removing redundant model calls and sharply cutting runtime on large files.
- **AI evaluation & ground-truth loop.** Compares AI verdicts with client-verified human judgments (tracked as F1) and feeds the gaps back into the engine, raising accuracy release over release.
- **Secure encrypted Excel processing.** Automated write-back to MIP-encrypted enterprise workbooks, with VBA macro preservation and subprocess isolation, in a locked-down compliance environment.
- **Concurrency tuning & packaging.** Worker pools, batch sizing and token budgets; shipped as a self-contained ~120 MB Windows executable that runs without Python.
- **Vector search APIs.** Python REST APIs over a FAISS vector store for similarity search and RAG. Optimising the vectorization pipeline cut processing time by **~39%**, approved as a formal Cost Saving Initiative.
- **Asana workflow automation.** Standalone tools with secure API integration, retries, structured logging and audit traceability, cutting manual effort by **~35–45%** across projects.

**OSS Development Project** (Aug 2024 – Jun 2025)
- Led Power Automate initiatives and cloud-based solutions. **ServiceNow ticket automation** (email capture → SharePoint → Teams alerts) cut ticket response time by **~30%**, and the client recognised the parallel-execution optimisation.

**WebUI Development Project** (Feb 2024 – Aug 2024)
- JavaScript UI enhancements integrated with an enterprise LLM API to streamline client workflows, plus mentoring teammates.

### Cognizant — Software Engineer Trainee
*Jan 2022 – Aug 2023*
- Built internal tooling for code analysis, performance monitoring and task automation, plus dashboards for project metrics
- Acknowledged by the customer for contributions to a vulnerability-scanner project

---

## 🔬 Research & talks

- **Co-authored a peer-reviewed whitepaper** on cost-reliability optimisation of enterprise LLMs: contextual-bandit model routing, conformal-prediction hallucination calibration and drift-aware feedback. Selected for Fujitsu Convention 2026; **Good Paper Award**
- **Authored a whitepaper on AI-driven soil precision analysis**, which received a **Paper Award** at Fujitsu Convention 2025
- Gave an internal **Tech Talk on AI-driven vulnerability analysis**

---

## 🏆 Awards

- **Platinum Award**, Fujitsu India GDC Annual Award (Jul 2026), for ownership, innovative problem-solving and AI & automation delivery
- **Good Paper Award**, Fujitsu Convention 2026
- **Silver Award**, Core Contributions & Project Excellence (Apr 2026), for the AI inspection-validation platform and RAG pipeline
- **Bronze Award**, Core Contributions & Project Excellence (2025), for the Operational Efficiency Tool and Power Automate initiatives
- **Big Thank You Award** (2025), with client recognition for the Operational Efficiency Tool and OSS projects
- **AI & DDM Award 2025**, Practical Case Competition (Fujitsu / 1EdTech certified)

## 📜 Certifications

- Google AI Professional Certificate (Google / Coursera, 2026)
- Microsoft Azure Fundamentals (**AZ-900**)
- Career Essentials in Generative AI (Microsoft & LinkedIn)
- Ethics in the Age of Generative AI (LinkedIn Learning)
- Clean Code (Udemy)
- Fujitsu AI Agent Pilot Workshop (2026)

---

## 🧰 Tech stack

- **Generative AI & LLM:** RAG · multi-step / agentic LLM pipelines · prompt engineering · LLM evaluation (ground truth, F1) · hallucination mitigation · confidence calibration · Azure OpenAI · Gemini · Model Context Protocol
- **Vector search & data:** FAISS · LanceDB · hybrid retrieval (BM25 + dense) · HuggingFace embeddings (multilingual-e5) · PostgreSQL · SQLite
- **Backend:** Python (asyncio, concurrency, type hints) · FastAPI · Flask · REST APIs · WebSockets · SQLAlchemy · pytest
- **ML:** scikit-learn · XGBoost · TF-IDF
- **Cloud & automation:** Microsoft Azure · AWS Lambda · Power Automate · Microsoft Graph API · ServiceNow · Asana API
- **Tools & practices:** Git · Azure DevOps · Linux · PyInstaller · openpyxl / win32com · structured logging · retry logic · observability · CI · Agile/Scrum
- **Also:** JavaScript · Bash · Java / Spring Boot

## 🎓 Education

**B.E., Mechatronics Engineering**, Sona College of Technology (Anna University), 2018 – 2022 · CGPA 8.6 / 10

---

## 📫 Get in touch

Email is the best way to reach me: **guruprasad30122000@gmail.com**. I'm happy to talk about GenAI engineering roles, LLM tooling or any of the projects above.
