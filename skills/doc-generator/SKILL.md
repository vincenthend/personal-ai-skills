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
