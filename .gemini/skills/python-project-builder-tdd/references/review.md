# Code Review Guidelines

This document provides a checklist and best practices for conducting code reviews.

## Review Principles:
*   **Constructive Feedback**: Focus on the code, not the person.
*   **Clarity and Readability**: Is the code easy to understand?
*   **Correctness**: Does the code behave as expected and meet requirements?
*   **Maintainability**: Is the code easy to change and extend in the future?
*   **Efficiency**: Are there obvious performance bottlenecks?

## Pre-Review Checklist (Developer):
1.  **Self-Review**: Have you reviewed your own code thoroughly?
2.  **Tests**: Are all new and existing tests passing? Is test coverage adequate for new code?
3.  **Linting/Formatting**: Have you run `uv run ruff check src/ tests/` and `uv run black src/ tests/`?
4.  **Documentation**: Are docstrings and comments up to date?
5.  **Requirements**: Does the code meet the specified requirements in `REQUIREMENTS.md`?

## Reviewer Checklist:
*   **Functionality**: Does the code do what it's supposed to do? (Check against `REQUIREMENTS.md`).
*   **Design**: Is the solution appropriate for the problem? Is it consistent with the overall architecture (`references/architecture.md`)?
*   **Readability/Style**:
    *   Does it follow PEP 8?
    *   Are variable/function names clear and descriptive?
    *   Are there appropriate comments/docstrings?
*   **Test Coverage**: Are new features/bug fixes covered by tests?
*   **Error Handling**: Are potential errors handled gracefully?
*   **Security**: Are there any obvious security vulnerabilities?
*   **Performance**: Are there any inefficient algorithms or database queries?
*   **Duplication**: Is there any unnecessary code duplication?
