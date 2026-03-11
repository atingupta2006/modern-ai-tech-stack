# Day 2 – Environment setup

The Day 2 notebooks run in a **production-like environment**: model names are loaded from config, optional tokens from `.env`, and there is no separate demo or dev mode. Use this guide to get the notebooks running with no code changes. Use **Python 3.11** and a **separate virtual environment for Day 2** (e.g. `.venv-day2`).

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

Use a **separate venv for each day** so dependencies don't conflict. For Day 2, create `.venv-day2` in the **day-2** folder.

**Windows (Command Prompt or PowerShell):**
```bash
cd day-2
python -m venv .venv-day2
.venv-day2\Scripts\activate
```

**Linux / macOS:**
```bash
cd day-2
python3 -m venv .venv-day2
source .venv-day2/bin/activate
```

## 3. Install dependencies

With the virtual environment activated:

```bash
pip install -r requirements.txt
```

This installs the packages required for Day 2: `transformers`, `datasets`, `sentence-transformers`, `faiss-cpu`, `chromadb`, `torch`, `torchvision`, `Pillow`, and `python-dotenv`. Other modules used (`json`, `os`, `pathlib`, `numpy`) are either in `requirements.txt` or part of the Python standard library.

**First-run note:** The first time you run a notebook, models are downloaded from Hugging Face Hub. This requires internet access and may take a few minutes depending on your connection. Models are cached locally after the first download.

## 4. Secrets (.env) and config (config.json)

- **Secrets (tokens):** Copy `.env.example` to `.env` in the **day-2** folder and set your Hugging Face token (optional; only needed for gated models). Do not commit `.env`.
  ```bash
  cp .env.example .env
  ```
  Edit `.env` and set:
  ```
  HF_TOKEN=your-huggingface-token-here
  ```
- **Config (non-secret settings):** The file `config.json` in the day-2 folder holds model names, embedding model, index type, and other settings. You can edit it if you want to use different models; the notebooks read it automatically. Do not put secrets in `config.json`.

Notebooks load `.env` and `config.json` in their first code cell. **Start Jupyter from the day-2 folder** so the paths resolve correctly.

## 5. Run the notebooks

Open the notebooks in Jupyter or your IDE and run cells **in order from top to bottom**. No edits to the code are required when:

- Python 3.11 is used
- The virtual environment (`.venv-day2`) is activated and `requirements.txt` is installed
- `.env` exists (optional; only for gated models)
- `config.json` is present in the day-2 folder
- You have internet access for downloading models on first run

## 6. Jupyter Notebook (included in requirements)

Jupyter Notebook is installed with `pip install -r requirements.txt`. Start it from the **day-2** folder so `.env` and `config.json` are found:

```bash
cd day-2
jupyter notebook
```

Then open `01-1-Open-Source-AI-Ecosystem.ipynb` to begin.

## 7. GPU (optional)

Day 2 notebooks work on CPU. A GPU speeds up model inference but is not required. If you have a CUDA-capable GPU and want to use it, install the GPU version of PyTorch separately before running `pip install -r requirements.txt`:

```bash
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu121
```

Colab users: GPU is available via Runtime > Change runtime type > GPU.
