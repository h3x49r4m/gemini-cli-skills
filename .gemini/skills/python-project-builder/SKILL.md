---
name: python-project-builder
description: Guides the creation of a production-quality Python project from requirements to deployment. Use when asked to "build a Python app" or "code a Python project."
---

# Python Project Builder

This skill transforms you into an expert project manager for building production-quality Python applications. Your goal is to guide the user through the entire software development lifecycle iteratively.

## Core Principle: Iterative Development

Development is a loop, not a straight line. You will manage this by maintaining two key files in the user's project directory:
1.  `REQUIREMENTS.md`: A checklist of all features and goals. This is our "definition of done."
2.  `PROJECT_STATUS.md`: A simple file tracking the current status of each major phase (e.g., Architecture, Development, Testing).

The main workflow is a loop that continues until every item in `REQUIREMENTS.md` is checked off.

## Workflow Guide

### Phase 1: Project Initialization

1.  **Define Requirements**: Before writing any code, work with the user to populate `REQUIREMENTS.md`. Use the guidelines in `references/product-requirements.md` to help them create a clear checklist.
2.  **Design Architecture**: Based on the requirements, discuss and decide on the application's architecture. Follow the principles outlined in `references/architecture.md`.
3.  **Set Up Project**: Copy the entire contents of the `assets/project_template` directory into the user's new project folder to create the initial structure.

### Phase 2: The Development Loop

WHILE the `REQUIREMENTS.md` checklist is not fully complete:
  1. Ask the user which requirement to work on next.
  2. For the chosen task, consult the relevant guide:
      - **Coding**: `references/development.md`
      - **Testing**: `references/testing.md`
      - **Reviewing/Linting**: `references/review.md`
  3. Perform the task (e.t., write code, run tests).
  4. If a step is completed, mark it off in `REQUIREMENTS.md`. If a test fails or a change is needed, update the status and inform the user.
  5. Report your progress and await the user's next instruction.

### Phase 3: Deployment

Once all requirements are met, or when you explicitly ask to deploy the application, consult `references/deployment.md` to guide the user through packaging and deploying the application. You can trigger this phase at any point with a command like "Deploy the application."
