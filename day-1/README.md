# Day 1 – APIs and Multimodal AI Workflows

Python for AI Workflows, Understanding AI APIs, Multimodal AI Integration, and building a multimodal assistant.

All notebooks assume a production-like setup: real API keys, config-driven URLs and models, and the same patterns you would use in production. There is no separate "demo" or "development" mode—participants run and extend code as in a production environment.

## Setup and running (no code changes required)

- **Python:** Use **Python 3.11**. Check with `python --version`.
- **Virtual environment:** Use a **separate venv per day**. For Day 1: create `.venv-day1` in the day-1 folder, activate it, then install dependencies.
  - Windows: `python -m venv .venv-day1` then `.venv-day1\Scripts\activate`
  - Linux/macOS: `python3 -m venv .venv-day1` then `source .venv-day1/bin/activate`
- **Dependencies:** From the `day-1` folder (with venv activated): `pip install -r requirements.txt`
- **Secrets:** Copy `.env.example` to `.env` and set `OPENAI_API_KEY`. Notebooks load `.env` in the first code cell; do not commit `.env`.
- **Config:** Non-secret settings (API base URL, model names) are in `config.json` in the day-1 folder; notebooks read it automatically.
- **Running:** Start **Jupyter Notebook** from the **day-1** folder (Jupyter is in `requirements.txt`). Run cells in order; no code changes are required. Internet access is needed for API calls and the optional `httpbin.org` example.

  **Step-by-step:** See **SETUP.md** for detailed setup.

## In-session material (core)

- **00-Python-Basics-Reference.ipynb** – Python basics reference (operators, types, control flow, lists, dicts, functions). Use when participants need grounding before or alongside the API material. No API key required; runnable on its own.
- **01-Python-and-AI-APIs.ipynb** – Python for AI, REST APIs, requests, error handling, logging. Diagram: API flow (Block A/B/C). Frameworks table.
- **02-Multimodal-AI-Integration.ipynb** – Text (primary), image (brief), speech (STT/TTS). Business-relevant scenarios. Pipeline diagram with blocks.
- **03-Multimodal-Assistant.ipynb** – End-to-end multimodal pipeline: voice/text → LLM → text/speech. Chains the patterns from notebooks 01 and 02 into a complete assistant.

The notebooks in this folder cover the Day 1 topics: Python for AI workflows, AI APIs, and multimodal integration.
