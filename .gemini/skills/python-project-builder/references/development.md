# Development Guidelines

This guide covers best practices for writing Python code in this project.

## Environment Setup:
1.  **Virtual Environment**: Always use a virtual environment (`python -m venv .venv`).
    *   Activate: `source .venv/bin/activate` (Linux/macOS) or `.\.venv\Scripts\activate` (Windows).
2.  **Dependency Management**: Use `poetry` as defined in `pyproject.toml`.
    *   Install dependencies: `poetry install`
    *   Add new dependency: `poetry add <package-name>`
    *   Add dev dependency: `poetry add --group dev <package-name>`

## Coding Standards:
*   **PEP 8**: Adhere to Python's official style guide.
*   **Type Hinting**: Use type hints for function signatures and variables to improve readability and catch errors early.
*   **Docstrings**: Write clear docstrings for modules, classes, and functions.
*   **Error Handling**: Use `try-except` blocks for anticipated errors; avoid bare `except` clauses.
*   **Logging**: Use Python's `logging` module for application events.

## Directory Structure (inside `src/`):
*   Organize code into logical modules and packages.
*   Avoid deeply nested directories without good reason.
*   Example:
    ```
    src/
    ├── __init__.py
    ├── main.py
    ├── config.py
    ├── api/
    │   ├── __init__.py
    │   └── v1/
    │       ├── __init__.py
    │       └── endpoints.py
    ├── services/
    │   ├── __init__.py
    │   └── user_service.py
    └── models/
        ├── __init__.py
        └── user_model.py
    ```
