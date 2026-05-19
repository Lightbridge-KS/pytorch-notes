# AGENTS.md - PyTorch Notes

This repo is a focused Quarto Book for PyTorch notes. Keep it flexible, runnable, and easy to grow chapter by chapter.

## Working Style

- Treat `~/my_book/pytorch-notes` as the repo root.
- Prefer small, incremental changes over large restructuring.
- Keep the book mostly notebook-first: use `.ipynb` for runnable tutorials, experiments, and worked examples.
- Use `.qmd` for prose-heavy summaries, cheatsheets, references, and short conceptual notes.
- Do not add placeholder chapters just to fill the outline. Add chapters when there is real content.

## Project Layout

- `contents/setup/` - environment, devices, installation, and workflow notes
- `contents/tensor/` - tensors, shapes, views, broadcasting, autograd basics
- `contents/data/` - datasets, transforms, DataLoader, splits, sampling
- `contents/nn/` - modules, layers, losses, optimizers, initialization
- `contents/training/` - loops, checkpointing, metrics, reproducibility, debugging
- `contents/workflows/` - complete examples with reasonably sized real datasets
- `contents/recipes/` - practical snippets and focused how-tos
- `data/` - small or documented local datasets for runnable examples
- `scripts/` - helper scripts for data download, cleanup, or maintenance
- `assets/images/` - book images and diagrams

## Environment

- Use project-local `uv` and `.venv`.
- Prefer `uv run ...` for commands.
- Keep dependencies in `pyproject.toml` and lock with `uv.lock`.
- Do not install packages globally for this repo.

Common commands:

```bash
uv sync
uv run quarto render
uv run ruff check .
```

## Quarto

- `_quarto.yml` is the source of truth for book structure.
- Use `freeze: auto`; commit relevant `_freeze/` output when executable chapters are added and rendered.
- Keep `execute-dir: project` so notebooks can use stable project-relative paths.
- Wire new chapters into `_quarto.yml` only when the chapter file exists and has useful content.
- Keep `index.qmd` concise; it is the book entry point, not a long table of contents.

## Notebook Conventions

- The first cell should be a Markdown H1 title.
- Use Markdown cells to explain intent before code.
- Keep notebooks runnable from a clean kernel.
- Prefer small, real datasets over synthetic examples when practical.
- Avoid long training runs by default. If an example trains, keep it lightweight and document expected runtime.
- Use deterministic seeds when results are shown.
- Store downloaded or generated data under `data/` with clear notes.

## Git

- Use Conventional Commits.
- Keep commits atomic: one chapter, workflow, or maintenance concern per commit.
- Do not commit `.venv/`, `_book/`, raw large datasets, or private/sensitive data.
- Before reporting success, run the smallest meaningful check, usually `uv run quarto render`.

