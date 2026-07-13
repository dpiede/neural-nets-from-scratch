# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

This is an early-stage, from-scratch neural network learning project (in the spirit of Andrej Karpathy's
"micrograd" tutorial). The current branch (`feature/micrograd`) is building an autograd engine and neural net
library from first principles.

As of now:
- `src/` is an empty package stub (only `.gitkeep`) — this is where the autograd engine / NN library code should go.
- `notebooks/micrograd_from_scatch.ipynb` is the working notebook (currently just has the `numpy`/`matplotlib` import
  cell); this is where the implementation is being built/exercised interactively.
- `main.py` is the default `uv init` placeholder entrypoint, not yet wired to any real code.
- `README.md` is empty.

Because there is no established architecture yet, don't assume patterns from memory (e.g. specific class names
like `Value`, `Neuron`, `Layer`, `MLP`) — check `src/` and the notebook for what actually exists before extending it.

## Environment and commands

Dependency management is via `uv` (see `pyproject.toml`, `uv.lock`, `.python-version` = 3.13).

- Install/sync dependencies: `uv sync`
- Run the main script: `uv run main.py`
- Run a Python snippet in the project env: `uv run python -c "..."`
- Launch Jupyter for notebook work: `uv run jupyter notebook` (or open `notebooks/` in an editor with Jupyter
  support using the `.venv` kernel)
- Add a dependency: `uv add <package>`

There is no linter, formatter, or test suite configured yet. If you add one, prefer wiring it through `uv` (e.g.
`uv add --dev pytest` and `uv run pytest`) and update this file with the actual commands.

## Working with the notebook

Substantial implementation work is happening in `notebooks/micrograd_from_scatch.ipynb`. When asked to implement
core logic (autograd `Value` objects, backward passes, layers/MLPs, training loops, etc.), prefer building it out
in the notebook to match the existing exploratory workflow, unless the user asks for it to live in `src/` as an
importable module instead.
