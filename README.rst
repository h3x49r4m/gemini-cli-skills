=============================
Gemini CLI Skills
=============================

A central repository for `Gemini CLI <https://github.com/google-gemini/gemini-cli>`_ skills.

Purpose
-------
This project aims to provide a structured and easily manageable collection of skills
that extend the capabilities of the Gemini CLI. Each skill encapsulates specialized
knowledge, workflows, or tool integrations, allowing the Gemini CLI to perform
a wider range of tasks efficiently.

Structure
---------
Skills are organized within the ``.gemini/skills/`` directory.
Each skill resides in its own subdirectory, containing:

*   ``SKILL.md``: The main definition and documentation for the skill.
*   ``assets/``: Any supporting assets like templates or images.
*   ``references/``: Supplementary documentation or guides.

Example::

    .gemini/skills/
    ├── python-project-builder-interactive/
    │   ├── SKILL.md
    │   ├── assets/
    │   └── references/
    ├── python-project-builder-tdd/
    │   ├── SKILL.md
    │   ├── assets/
    │   └── references/
    └── another-skill/
        └── SKILL.md


Usage
-----
Skills extend the capabilities of the Gemini CLI by providing specialized knowledge and workflows.

**1. Skill Discovery and Activation:**
    The Gemini CLI continuously monitors its designated skill directories (e.g., ``.gemini/skills/``)
    for new or updated skills. When a user's request aligns with a skill's
    ``description`` (defined in its ``SKILL.md``), the CLI may choose to
    ``activate_skill``.

    For example, if a skill has the description "Guides the creation of a
    production-quality Python project...", the Gemini CLI might activate
    it in response to a prompt like "build a Python app".

    Once activated, the skill's ``instructions`` and ``available_resources``
    are made available to the agent, guiding its subsequent actions.

    **Available Skills:**

    *   **python-project-builder-interactive**: Guides the creation of a production-quality Python project using an iterative development approach from requirements to deployment. Use when asked to "build a Python app" or "code a Python project."

    *   **python-project-builder-tdd**: Similar to the interactive builder but follows Test-Driven Development (TDD) methodology with Red-Green-Refactor cycles. Use when asked to "build a Python app using TDD" or "code a Python project with test-driven development."

**2. Managing Skills:**
    *   **Adding/Updating Skills**: To add a new skill or update an existing one,
        create/modify its directory and ``SKILL.md`` within ``.gemini/skills/``.
        For structured skill development, consider using the ``skill-creator``
        skill itself.

    *   **Reloading Skills**: If you manually change skill files, use the
        ``/skills reload`` command in the CLI to ensure the Gemini CLI
        recognizes the changes without restarting.

**3. Gemini CLI Commands:**
    The Gemini CLI provides commands to manage skills:

    *   **/skills list**: Lists all skills discovered by the Gemini CLI.
        This command shows the name and description of each skill, helping users
        to identify available functionalities.

        Example usage in Gemini CLI::

            /skills list

    *   **/skills reload**: Reloads all skills from their respective directories.
        Use this command after adding, removing, or modifying skill files
        (e.g., ``SKILL.md``) to ensure the Gemini CLI recognizes the changes
        without requiring a full restart.

        Example usage in Gemini CLI::

            /skills reload

For more details on skill creation and advanced usage, refer to the Gemini CLI documentation.

Contributing
------------
Contributions to this skill repository are welcome.
Please ensure any new skills or updates adhere to the established structure
and provide clear documentation.
