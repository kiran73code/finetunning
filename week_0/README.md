# Week 0 
-- It's  simple huggingface job and endpoint setup and testing


## Overview
- Small project with examples in `week_0/` demonstrating model inference and a simple runner.

## Requirements
- Python 3.11+ recommended
- A POSIX shell (Linux / macOS)

## Recreate the virtual environment (venv)
1. sync the uv project virtual environment named `.venv`:

```bash
uv sync --all-extras
```

2. Activate the venv:

On Linux/macOS:

```bash
source .venv/bin/activate
```

On Windows (PowerShell):

```powershell
.\.venv\Scripts\Activate.ps1
```

## Project layout
- `week_0/` — example scripts and local virtual environment
- `week_0/src/` — `inference_sample.py`, `main.py`

## Notes
- The repository does not include a `requirements.txt` by default; use `pyproject.toml` or create a `requirements.txt` with `pip freeze > requirements.txt` after setting up the environment.
- If you want a reproducible environment, consider using `poetry` or `pip-tools` to lock dependencies.

If you'd like, I can also add a `requirements.txt` generated from the current venv or add a short run script (`make` or `scripts/`) to simplify these commands.


#### Steps to setup HF job and inference endpoints.

1. Update the HF account to pro subscription
2. For endpoint serving deploy small model like Qwen 

-  Running hf job
```python
hf jobs uv run --flavor a10g-small main.py --input_text "'The answer is 42'"
```

- Running the simple inference endpoint calling script
```python
python inference_sample.py "The capital of France is" --model "Qwen/Qwen3-0.6B-Base" --max_tokens 1024
```