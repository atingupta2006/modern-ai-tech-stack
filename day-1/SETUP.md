# Day 1 – Environment setup

The Day 1 notebooks run in a **production-like environment**: config and secrets are loaded from files, API calls use the same endpoints and patterns as in production, and there is no separate demo or dev mode. Use this guide to get the notebooks running with no code changes. Use **Python 3.11** and a **separate virtual environment for Day 1** (e.g. `.venv-day1`).

## 1. Python version

Use **Python 3.11**. The notebooks use type hints (e.g. `str | None`, `list[dict]`) that require Python 3.10+; the course standard is 3.11.

Check your version:
```bash
python --version
```
or
```bash
python3 --version
```

## 2. Create a virtual environment (one per day)

Use a **separate venv for each day** so dependencies don’t conflict. For Day 1, create `.venv-day1` in the **day-1** folder (or in the repo root).

**Windows (Command Prompt or PowerShell):**
```bash
cd day-1
python -m venv .venv-day1
.venv-day1\Scripts\activate
```

**Linux / macOS:**
```bash
cd day-1
python3 -m venv .venv-day1
source .venv-day1/bin/activate
```

## 3. Install dependencies

With the virtual environment activated:

```bash
pip install -r requirements.txt
```

This installs the packages required for Day 1 (`requests`, `python-dotenv`). Other modules used in the notebooks (`json`, `os`, `logging`, `csv`, `io`, `uuid`, `time`, `pathlib`) are part of the Python standard library.

## 4. Secrets (.env) and config (config.json)

- **Secrets (API keys):** Copy `.env.example` to `.env` in the **day-1** folder and set your keys. Do not commit `.env`.
  ```bash
  cp .env.example .env
  ```
  Edit `.env` and set:
  ```
  OPENAI_API_KEY=your-openai-api-key-here
  ```
- **Config (non-secret settings):** The file `config.json` in the day-1 folder holds API base URL, model names, and timeouts. You can edit it if you use a different provider or model; the notebooks read it automatically. Do not put secrets in `config.json`.

Notebooks load `.env` and `config.json` in their first code cell. **Start Jupyter from the day-1 folder** so the paths resolve correctly.

## 5. Run the notebooks

Open the notebooks in Jupyter or your IDE and run cells **in order from top to bottom**. No edits to the code are required when:

- Python 3.11 is used
- The virtual environment (e.g. `.venv-day1`) is activated and `requirements.txt` is installed
- `.env` exists with `OPENAI_API_KEY` set (for API-dependent cells)
- `config.json` is present in the day-1 folder
- You have internet access for API calls (and for the optional `httpbin.org` example in the first notebook)

## 6. Jupyter Notebook (included in requirements)

Jupyter Notebook is installed with `pip install -r requirements.txt`. Start it from the **day-1** folder so `.env` and `config.json` are found:

```bash
cd day-1
jupyter notebook
```

Then open `01-Python-and-AI-APIs.ipynb`, `02-Multimodal-AI-Integration.ipynb`, or `03-Multimodal-Assistant.ipynb`.
