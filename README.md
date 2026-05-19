# PyTorch Notes

Focused PyTorch notes as a Quarto Book, mostly written as runnable Jupyter notebooks.

Published site: <https://pytorch-notes-lightbridge.netlify.app>

## Local workflow

```bash
uv sync
uv run quarto render
```

The book uses `freeze: auto` so executed notebook output can be committed for local-first publishing.
