# Day 3 – Setup Guide

## 1. Prerequisites

| Requirement | Check |
|---|---|
| Python 3.11 | `python --version` |
| pip | `pip --version` |
| OpenAI API key | Sign up at https://platform.openai.com |
| Internet access | Required for API calls and first-time model downloads |

## 2. Create a virtual environment

Create a **separate** virtual environment for Day 3 (do not reuse Day 1 or Day 2 venvs):

```bash
cd day-3
python -m venv .venv-day3
```

Activate it:

- **Windows:** `.venv-day3\Scripts\activate`
- **Linux/macOS:** `source .venv-day3/bin/activate`

Verify:

```bash
python --version   # should show 3.11.x
which python       # should point to .venv-day3
```

## 3. Install dependencies

```bash
pip install -r requirements.txt
```

This installs: langchain-core, langchain, langchain-openai, langchain-community, chromadb, sentence-transformers, faiss-cpu, numpy, python-dotenv, notebook, jupyter.

## 4. Set up environment variables

```bash
cp .env.example .env
```

Edit `.env` and set your keys:

```
OPENAI_API_KEY=sk-...
HF_TOKEN=hf_...          # optional, only for gated models
```

**Do not commit `.env`** — it is already in `.gitignore`.

## 5. Configuration

Non-secret settings are in `config.json`:

```json
{
  "embedding_model": "all-MiniLM-L6-v2",
  "llm_model": "gpt-4o-mini",
  "chunk_size": 500,
  "chunk_overlap": 50,
  "chroma_collection_name": "day3_demo",
  "retriever_top_k": 3,
  "temperature": 0.0
}
```

No changes are required. If you want to use a different OpenAI model (e.g., `gpt-4o`), update `llm_model`.

## 6. Run notebooks

```bash
jupyter notebook
```

Open notebooks in order (01 → 02 → 03 → 04 → 05). Run cells top to bottom.

## 7. Notes

- **API costs:** Day 3 uses the OpenAI API. The default model (`gpt-4o-mini`) is cost-effective. All notebooks use small document sets and short prompts to minimize token usage.
- **Offline embedding:** The sentence-transformers embedding model (`all-MiniLM-L6-v2`) runs locally — no API calls for embeddings.
- **GPU:** Not required. All embedding and vector search operations run on CPU. LLM inference is via the OpenAI API.
- **Fallback mode:** Notebooks that call the OpenAI API include `if not API_KEY:` guards with simulated responses so you can review the flow without a key.
