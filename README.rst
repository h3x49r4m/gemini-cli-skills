=============================
Gemini CLI Skills Repository
=============================

A central repository for `Gemini CLI <https://gemini.google.com/cli>`_ skills.

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
    ├── python-project-builder/
    │   ├── SKILL.md
    │   ├── assets/
    │   └── references/
    └── another-skill/
        └── SKILL.md


Usage
-----
To add a new skill, create a new directory under ``.gemini/skills/``
and populate it with the necessary ``SKILL.md`` and supporting files.

The Gemini CLI automatically discovers skills located in its designated skill directories.
Once a skill is defined, it can be activated within a conversation
using the ``activate_skill`` command, following the instructions provided
by the skill itself.

For more details on skill creation and usage, refer to the Gemini CLI documentation.

Contributing
------------
Contributions to this skill repository are welcome.
Please ensure any new skills or updates adhere to the established structure
and provide clear documentation.
