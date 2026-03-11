# Day 3 – LangChain, RAG and Responsible AI

LangChain framework, Retrieval-Augmented Generation, AI evaluation, responsible AI practices, and a capstone project combining all three days.

All notebooks assume a production-like setup: model names and parameters are loaded from `config.json`, API keys from `.env`, and the same patterns you would use in production. There is no separate "demo" or "development" mode — participants run and extend code as in a production environment.

## Setup and running (no code changes required)

- **Python:** Use **Python 3.11**. Check with `python --version`.
- **Virtual environment:** Use a **separate venv per day**. For Day 3: create `.venv-day3` in the day-3 folder, activate it, then install dependencies.
  - Windows: `python -m venv .venv-day3` then `.venv-day3\Scripts\activate`
  - Linux/macOS: `python3 -m venv .venv-day3` then `source .venv-day3/bin/activate`
- **Dependencies:** From the `day-3` folder (with venv activated): `pip install -r requirements.txt`
- **Secrets:** Copy `.env.example` to `.env` and set `OPENAI_API_KEY` (required for LangChain LLM calls). Optionally set `HF_TOKEN` for gated models. Notebooks load `.env` in the first code cell; do not commit `.env`.
- **Config:** Non-secret settings (model names, chunk settings, retriever parameters) are in `config.json` in the day-3 folder; notebooks read it automatically.
- **Running:** Start **Jupyter Notebook** from the **day-3** folder. Run cells in order; no code changes are required. Internet access is needed for API calls and first-time model downloads.

  **Step-by-step:** See **SETUP.md** for detailed setup.

## In-session material (core)

- **01-1-LangChain-Framework.ipynb** – LangChain architecture (diagram), prompt templates, chains (LCEL), tools and agents, connecting LangChain with vector databases (retriever pattern). Code-to-architecture mapping throughout.
- **02-1-RAG-Fundamentals.ipynb** – RAG pipeline (diagram), hallucination reduction through retrieval, naive RAG implementation, hybrid RAG overview, retrieve-and-rerank concept. Full code-to-architecture walkthrough.
- **03-1-Evaluation-and-Responsible-AI.ipynb** – Practical evaluation of AI responses, prompt testing and validation, human-in-the-loop review, bias and fairness, explainability, governance, enterprise trust.
- **04-1-Lab-Document-QA-Assistant.ipynb** – End-to-end lab: build a document-based question answering assistant using LangChain and vector search. Pipeline diagram mapped to numbered code blocks.
- **05-1-Capstone-AI-Assistant.ipynb** – Mini capstone: design and present a working AI assistant combining APIs (Day 1), embeddings (Day 2), and RAG (Day 3). Architecture diagram, scaffold code, presentation criteria.

## Assessments

- **00-1-pre.md** – Pre-assessment (live form link)
- **01-2-day-3-nb-1.md** – Post-assessment for Notebook 01 (live form link)
- **02-2-day-3-nb-2.md** – Post-assessment for Notebook 02 (live form link)
- **03-2-day-3-nb-3.md** – Post-assessment for Notebook 03 (live form link)
- **04-2-day-3-nb-4.md** – Post-assessment for Notebook 04 (live form link)
- **05-2-day-3-nb-5.md** – Post-assessment for Notebook 05 (live form link)
