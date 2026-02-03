# Project Name

This is a boilerplate Python project, managed by the `python-project-builder` Gemini CLI skill.

## Setup

1.  **Install `uv`**: If you don't have `uv` installed, get it from `pip install uv`.
2.  **Initialize environment & install dependencies**: `uv pip install -e .` This will create a `.venv` if it doesn't exist and install all dependencies listed in `pyproject.toml`.

## Development

Write your application code in the `src/` directory.

## Testing

Run tests using pytest: `uv run pytest`

## Linting & Formatting

Check code style with ruff and black: `uv run ruff check .` and `uv run black .`
