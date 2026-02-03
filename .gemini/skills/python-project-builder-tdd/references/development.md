# Development Guidelines

This guide covers best practices for writing Python code in this project.

## Environment Setup:
1.  **Dependency Management**: This project uses `uv` for dependency management, based on `pyproject.toml` (PEP 621).
    *   **Install all dependencies**: `uv pip install -e .` (This will also create a virtual environment if one doesn't exist).
    *   **Add new dependency**: `uv add <package-name>`
    *   **Add new dev dependency**: `uv add <package-name> --group dev`
    *   **Run scripts/commands**: Use `uv run <command>`. For example, `uv run python src/main.py`.

## Coding Standards:
*   **PEP 8**: Adhere to Python's official style guide.
*   **Type Hinting**: Use type hints for function signatures and variables to improve readability and catch errors early.
*   **Docstrings**: Write clear docstrings for modules, classes, and functions.
*   **Error Handling**: Use `try-except` blocks for anticipated errors; avoid bare `except` clauses.
*   **Logging**: Use Python's `logging` module for application events.

## Test-Driven Development (TDD): The "Green" Phase
When implementing a new feature or fixing a bug, follow the "Green" phase of TDD:
1.  **Write Minimal Code**: After writing a failing test (the "Red" phase), write *only* the code necessary to make that specific test pass. Avoid writing ahead or adding functionality not covered by the current failing test.
2.  **Focus on Functionality**: The primary goal in this phase is to achieve a passing test. Code quality and elegance can be improved during the "Refactor" phase.
3.  **Run Tests Frequently**: After every small code change, run the relevant tests to ensure you've achieved a "Green" state and haven't introduced regressions.



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
