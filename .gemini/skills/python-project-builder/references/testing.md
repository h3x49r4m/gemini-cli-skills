# Testing Guidelines

This document outlines how to write and run tests for your Python project using `pytest`.

## Principles:
*   **Test Pyramid**: Aim for more unit tests, fewer integration tests, and even fewer end-to-end tests.
*   **Arrange-Act-Assert (AAA)**: Structure your tests with these three phases.
*   **Isolation**: Tests should be independent and not rely on the state of other tests.
*   **Readability**: Tests should be easy to understand.

## Using `pytest`:
*   **Installation**: `poetry add --group dev pytest` (already in `pyproject.toml`)
*   **Running Tests**: `poetry run pytest` (from the project root).
    *   To run specific tests: `poetry run pytest tests/path/to/module.py::test_function`
    *   Show verbose output: `poetry run pytest -v`
    *   Stop on first failure: `poetry run pytest -x`
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
*   Installation: `poetry add --group dev pytest-cov`
*   Run with coverage: `poetry run pytest --cov=src`
*   Generate HTML report: `poetry run pytest --cov=src --cov-report=html`
