# neural-nets-from-scratch

![Python 3.13+](https://img.shields.io/badge/python-3.13%2B-blue)
![uv](https://img.shields.io/badge/deps-uv-de5fe9)
![License: MIT](https://img.shields.io/badge/license-MIT-green)

Building neural networks and an autograd engine from first principles, in the spirit of Andrej Karpathy's
[micrograd](https://github.com/karpathy/micrograd) tutorial.

## Project state

Early-stage / learning project. Work is happening interactively in `notebooks/micrograd_from_scatch.ipynb`,
building up a small `Value` autograd engine (scalar-valued backprop) and, eventually, `Neuron`/`Layer`/`MLP`
abstractions on top of it.

## Layout

- `notebooks/` — exploratory notebooks; this is where core logic is being built and exercised
- `src/` — package stub for code once it graduates out of the notebook
- `main.py` — placeholder entrypoint

## Setup

Dependencies are managed with [uv](https://docs.astral.sh/uv/).

```bash
uv sync
```

Graphviz's `dot` binary is also required (for rendering computation graphs) and must be installed separately
via your system package manager, e.g.:

```bash
sudo apt-get install graphviz
```

## Usage

```bash
uv run main.py
```

To work in the notebooks:

```bash
uv run jupyter notebook
```

or open `notebooks/` in an editor with Jupyter support, using the `.venv` kernel.
