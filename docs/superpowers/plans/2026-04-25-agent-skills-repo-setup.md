# Agent Skills Repository Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Initialize a Git repository with a `doc-generator` sample skill and a cross-agent README.

**Architecture:** Namespaced `skills/` directory for organization. Standard `SKILL.md` format for Gemini CLI compatibility.

**Tech Stack:** Git, Markdown.

---

### Task 1: Repository Infrastructure

**Files:**
- Create: `.gitignore`

- [ ] **Step 1: Create .gitignore**

```text
# Gemini CLI package files
*.skill

# OS files
.DS_Store
Thumbs.db

# Local environment
.env
.venv/
node_modules/
```

- [ ] **Step 2: Commit**

```bash
git add .gitignore
git commit -m "chore: initial infrastructure"
```

---

### Task 2: Implement `doc-generator` Skill

**Files:**
- Create: `skills/doc-generator/SKILL.md`
- Create: `skills/doc-generator/assets/templates/tech-spec.md`

- [ ] **Step 1: Create Technical Spec template**

```markdown
# Technical Specification: {{project_name}}

## 1. Overview
{{description}}

## 2. Architecture
{{architecture_details}}

## 3. API Reference
{{api_details}}

## 4. Testing Strategy
{{testing_details}}
```

- [ ] **Step 2: Create SKILL.md**

```markdown
---
name: doc-generator
description: Generate structured technical documents using templates. Use when the user asks to "create a tech spec", "write a document", or "generate a report" based on project context.
---

# Document Generator

This skill helps you generate consistent documentation by using templates stored in the `assets/templates/` directory.

## Workflow

1. Identify the document type requested.
2. Read the template from `assets/templates/`.
3. Fill placeholders (e.g., {{project_name}}) using provided context.
4. Output the final Markdown document.

## Templates Available

- `tech-spec.md`: Use for technical design and project specifications.
```

- [ ] **Step 3: Commit**

```bash
git add skills/doc-generator/
git commit -m "feat: add doc-generator skill"
```

---

### Task 3: Universal README

**Files:**
- Create: `README.md`

- [ ] **Step 1: Write README.md content**

```markdown
# Shared Agent Skills

A repository for sharing AI agent skills across computers.

## Setup for Gemini CLI

1. Clone this repo: `git clone <repo-url>`
2. Install a skill:
   ```bash
   # From root
   gemini skills install ./skills/doc-generator/SKILL.md --scope workspace
   ```
3. Reload: `/skills reload`

## Setup for Claude / Codex

Point the agent to the `skills/` directory or copy the content of any `SKILL.md` into your system instructions to enable that skill's logic.
```

- [ ] **Step 2: Commit**

```bash
git add README.md
git commit -m "docs: add setup instructions"
```
