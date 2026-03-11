# Day 2 – Open-Source Models, Embeddings and Vector Search

Open-source AI models with Hugging Face, text embeddings, semantic similarity, and vector databases (FAISS, Chroma).

All notebooks assume a production-like setup: model names are loaded from `config.json`, optional tokens from `.env`, and the same patterns you would use in production. There is no separate "demo" or "development" mode — participants run and extend code as in a production environment.

## Setup and running (no code changes required)

- **Python:** Use **Python 3.11**. Check with `python --version`.
- **Virtual environment:** Use a **separate venv per day**. For Day 2: create `.venv-day2` in the day-2 folder, activate it, then install dependencies.
  - Windows: `python -m venv .venv-day2` then `.venv-day2\Scripts\activate`
  - Linux/macOS: `python3 -m venv .venv-day2` then `source .venv-day2/bin/activate`
- **Dependencies:** From the `day-2` folder (with venv activated): `pip install -r requirements.txt`
- **Secrets:** Copy `.env.example` to `.env` and set `HF_TOKEN` (optional; required only for gated models). Notebooks load `.env` in the first code cell; do not commit `.env`.
- **Config:** Non-secret settings (model names, index type) are in `config.json` in the day-2 folder; notebooks read it automatically.
- **Running:** Start **Jupyter Notebook** from the **day-2** folder. Run cells in order; no code changes are required. Internet access is needed for downloading models on first run.

  **Step-by-step:** See **SETUP.md** for detailed setup.

## In-session material (core)

- **01-1-Open-Source-AI-Ecosystem.ipynb** – Role of open-source AI in enterprise, Hugging Face ecosystem overview (Hub, transformers, datasets), browsing models and datasets, frameworks quick reference.
- **02-1-Working-with-Hugging-Face-Models.ipynb** – Four HF pipeline tasks: text summarization, question answering, sentiment analysis, image classification. One enterprise scenario and full runnable code per task.
- **03-1-Embeddings-and-Vector-Search.ipynb** – Embedding concept, semantic similarity with cosine distance, vector databases (FAISS and Chroma), retrieval pipeline end-to-end with code-to-architecture mapping.
- **04-1-Lab-Semantic-Document-Search.ipynb** – End-to-end lab: embed documents with sentence-transformers, build a FAISS index, query with natural language, retrieve top-k results. Pipeline diagram mapped to code blocks.

## Assessments

- **00-1-pre.md** – Pre-assessment (live form link)
- **01-2-day-2-nb-1.md** – Post-assessment for Notebook 01 (live form link)
- **02-2-day-2-nb-2.md** – Post-assessment for Notebook 02 (live form link)
- **03-2-day-2-nb-3.md** – Post-assessment for Notebook 03 (live form link)
- **04-2-day-2-nb-4.md** – Post-assessment for Lab (live form link)

The notebooks in this folder cover the Day 2 topics: open-source AI ecosystem, Hugging Face models, embeddings, and vector search.
