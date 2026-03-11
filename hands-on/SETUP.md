# Student Lab Pack – Environment Setup

The Student Lab Pack notebooks run in a **production-like environment**: config and secrets are loaded from files, API calls use the same endpoints and patterns as in production. Use this guide to get the notebooks running with no code changes. Use **Python 3.11** and a **separate virtual environment** (e.g. `.venv-student`).

## 1. Python version

Use **Python 3.11**. Check your version:
```bash
python --version
```

## 2. Create a virtual environment

**Windows (Command Prompt or PowerShell):**
```bash
cd hands-on
python -m venv .venv-student
.venv-student\Scripts\activate
```

**Linux / macOS:**
```bash
cd hands-on
python3 -m venv .venv-student
source .venv-student/bin/activate
```

## 3. Install dependencies

With the virtual environment activated:

```bash
pip install -r requirements.txt
```

This installs:
- **Day 1:** `requests`, `python-dotenv`, `notebook`, `jupyter`
- **Day 2:** `transformers`, `sentence-transformers`, `faiss-cpu`, `torch`, `numpy`

> **Note:** Day 2 packages include PyTorch (~2 GB download). If bandwidth is limited, install Day 1 packages first and add Day 2 packages before the second day:
> ```bash
> pip install requests python-dotenv notebook jupyter          # Day 1 only
> pip install transformers sentence-transformers faiss-cpu torch  # Add before Day 2
> ```

## 4. Secrets (.env) and config (config.json)

- **Secrets:** Copy `.env.example` to `.env` and set your API key. Do not commit `.env`.
  ```bash
  cp .env.example .env
  ```
  Edit `.env`:
  ```
  OPENAI_API_KEY=your-openai-api-key-here
  ```
- **Config:** `config.json` holds API base URL, model names, and timeouts. Edit if using a different provider.

## 5. Notebooks

| Day | Notebook | Topics |
|-----|----------|--------|
| 1 | `01-1-Python-and-AI-APIs.ipynb` | Python workflows, REST APIs, config, error handling, logging |
| 1 | `02-Multimodal-AI-and-Assistant.ipynb` | Text/image/speech APIs, multimodal pipeline lab |
| 2 | `03-HuggingFace-Embeddings-VectorSearch.ipynb` | HF models, embeddings, FAISS, semantic search lab |

Supporting files:
- `00-2-Python-Basics-Reference.ipynb` — Python refresher (optional, no API key needed)
- `tickets.csv` — sample data used in Day 1 and Day 2 labs

## 6. Run the notebooks

Start Jupyter from the **hands-on** folder so `.env` and `config.json` resolve correctly:

```bash
cd hands-on
jupyter notebook
```

Run cells **in order from top to bottom**. No code edits required when:
- Python 3.11 is used
- `.venv-student` is activated with `requirements.txt` installed
- `.env` exists with `OPENAI_API_KEY` set (Day 1)
- `config.json` is present
- Internet access available for API calls (Day 1) and model downloads (Day 2, first run)

## 7. Pre-downloading HF models (optional, recommended for class)

To avoid slow downloads during Day 2, pre-download the models:

```bash
python -c "from transformers import pipeline; pipeline('summarization', model='Falconsai/text_summarization')"
python -c "from transformers import pipeline; pipeline('sentiment-analysis')"
python -c "from transformers import pipeline; pipeline('question-answering')"
python -c "from sentence_transformers import SentenceTransformer; SentenceTransformer('all-MiniLM-L6-v2')"
```
