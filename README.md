# PySCF notebooks

This is a collection of Jupyter notebooks on various topics that employ PySCF.
I originally created these notebooks for my own use, but decided to share them because they could be useful to others.

View at https://EgorTrushin.github.io/pyscf-notebooks/

## Installation

Clone the repository, then set up the environment in one of two ways.

### With uv

[uv](https://docs.astral.sh/uv/) sets up everything and installs the exact versions recorded in `uv.lock`:

```bash
uv sync
```

This creates the virtual environment `.venv/` using the Python version from `.python-version` (3.12). Prefix commands with `uv run` to use the environment, e.g. `uv run jupyter lab`, or activate it once with `source .venv/bin/activate`.

### With python3 and pip

Without uv, create the virtual environment with `python3` (3.12 or newer) and install the pinned packages from `requirements.txt`:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

The notebooks import helper modules from `notebooks/sets/` and read data from `notebooks/json/` relative to their own directory, which is where Jupyter starts each notebook.

## Building the book

The book uses Jupyter Book 1 (`_config.yml`, `_toc.yml`); Jupyter Book 2 is not compatible with this layout. Build the HTML into `_build/html/` with

```bash
uv run jupyter-book build .
```

All notebooks are re-executed on each build.