# Design Spec: Agent Skills Repository

**Date:** 2026-04-25
**Topic:** Initializing a cross-agent compatible skill repository for sharing between computers.

## 1. Overview
The goal is to create a Git repository that serves as a centralized hub for AI agent "skills". These skills will be primarily designed for the Gemini CLI but structured to be easily portable to other agents like Claude or Codex.

## 2. Repository Structure
The repository will use a namespaced `skills/` directory to keep the root clean and organized.

```text
ai-skills/
├── .gitignore          # Standard Git ignores + .skill package files
├── README.md           # Instructions for Gemini, Claude, and Codex
└── skills/             # Container for all skills
    └── doc-generator/  # Sample Skill
        ├── SKILL.md    # Core instructions and metadata
        └── assets/     # Supporting templates and assets
            └── templates/
                └── tech-spec.md
```

## 3. Component Details

### 3.1 `doc-generator` Skill
A template-driven document generation skill.
- **SKILL.md**: Instructions for the agent to find templates in `assets/templates/` and fill them based on context.
- **Template (`tech-spec.md`)**: A Markdown file with placeholders for technical documentation.

### 3.2 `README.md` (Installation Guide)
This file is critical for the "shareable" nature of the repo. It will cover:
- **Gemini CLI**: How to package and install using `gemini skills install`.
- **Claude/Codex**: How to point the agent to the directory or copy-paste `SKILL.md` content as a "System Prompt" extension.

## 4. Implementation Plan
1. Initialize the directory structure.
2. Create the `.gitignore`.
3. Implement the `doc-generator` skill (SKILL.md and assets).
4. Write the `README.md` with multi-agent instructions.
5. Commit the initial structure to Git.

## 5. Success Criteria
- The repo is initialized with Git.
- The `doc-generator` skill is functional and follows the `SKILL.md` standard.
- The `README.md` clearly explains how to use the repo on a second computer.
