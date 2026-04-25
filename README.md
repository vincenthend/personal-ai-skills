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
