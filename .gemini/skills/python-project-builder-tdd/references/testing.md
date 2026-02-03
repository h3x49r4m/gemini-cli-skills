# Testing Guidelines

This document outlines how to write and run tests for your Python project using `pytest`.

## Principles:
*   **Test-Driven Development (TDD)**: Always write a failing test before writing the code that makes it pass. Follow the Red-Green-Refactor cycle.
*   **Test Pyramid**: Aim for more unit tests, fewer integration tests, and even fewer end-to-end tests.
*   **Arrange-Act-Assert (AAA)**: Structure your tests with these three phases.
*   **Isolation**: Tests should be independent and not rely on the state of other tests.
*   **Readability**: Tests should be easy to understand.

## Test-Driven Development (TDD): The "Red" and "Refactor" Phases

### The "Red" Phase (Write a Failing Test)
1.  **Understand the Requirement**: Before writing any code for a new feature or bug fix, clearly understand the desired behavior.
2.  **Write a Specific Test**: Create a new test case (or modify an existing one) that *specifically* targets the new behavior. This test should use `pytest` assertions to verify the expected outcome.
3.  **Ensure Failure**: Run only this new test. It *must* fail. This confirms that the test is correctly set up and that the desired functionality is indeed missing. If it passes, either the functionality already exists (and the test is redundant) or the test is flawed.

### The "Refactor" Phase (Improve Code Quality)
1.  **Clean Up Code**: Once your tests are green, look for opportunities to improve the code. This includes:
    *   Removing duplication.
    *   Improving naming and clarity.
    *   Extracting methods or classes.
    *   Simplifying complex logic.
2.  **Clean Up Tests**: Refactoring isn't just for production code. Improve your test suite by making tests more readable, maintainable, and efficient.
3.  **Maintain Green Bar**: After each small refactoring step, run all relevant tests to ensure that you haven't introduced any regressions. The goal is to improve the code without changing its external behavior.


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
