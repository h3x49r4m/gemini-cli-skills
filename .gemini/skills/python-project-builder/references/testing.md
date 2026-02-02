# Testing Guidelines

This document outlines how to write and run tests for your Python project using `pytest`.

## Principles:
*   **Test Pyramid**: Aim for more unit tests, fewer integration tests, and even fewer end-to-end tests.
*   **Arrange-Act-Assert (AAA)**: Structure your tests with these three phases.
*   **Isolation**: Tests should be independent and not rely on the state of other tests.
*   **Readability**: Tests should be easy to understand.

## Using `pytest`:
*   **Installation**: `uv add pytest --group dev` (already specified in `pyproject.toml` `[project.optional-dependencies.dev]`)
*   **Running Tests**: `uv run pytest` (from the project root).
    *   To run specific tests: `uv run pytest tests/path/to/module.py::test_function`
    *   Show verbose output: `uv run pytest -v`
    *   Stop on first failure: `uv run pytest -x`
*   **Test Files**:
    *   Place test files in the `tests/` directory.
    *   Name test files `test_*.py` or `*_test.py`.
    *   Name test functions `test_*`.

## Types of Tests:
*   **Unit Tests**: Test individual functions or methods in isolation.
    *   Use `unittest.mock` for mocking dependencies.
*   **Integration Tests**: Test the interaction between several units or components.
*   **Functional/Acceptance Tests**: Test a feature from an end-user perspective, often against the `REQUIREMENTS.md` acceptance criteria.

## Code Coverage:
*   Use `pytest-cov` to measure test coverage.
*   Installation: `uv add pytest-cov --group dev`
*   Run with coverage: `uv run pytest --cov=src`
*   Generate HTML report: `uv run pytest --cov=src --cov-report=html`
