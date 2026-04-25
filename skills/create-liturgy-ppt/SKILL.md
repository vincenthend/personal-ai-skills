---
name: create-liturgy-ppt
description: Read user-provided PDF files about church liturgy and create a PowerPoint presentation based on established templates. Use when the user asks to create a PowerPoint or slides for a liturgy or church service using a template.
---

# Create Liturgy PPT

## Quick Start
This skill will help you generate a church liturgy PowerPoint presentation (`KU_YYYY-MM-DD.pptx`) based on a template and a user-provided PDF.

## 1. Setup Process
1. **Create a Folder**: Create a new folder for the specific liturgy (e.g., named by date like `YYYY-MM-DD` or `KU_YYYY-MM-DD`) in the workspace root.
2. **Copy the Template**: Before making edits, use the terminal to copy the template file (e.g., `templates\PPT KU PAGI - Template.pptx`) into the new folder and rename it to `KU_YYYY-MM-DD.pptx` (replacing the date accordingly). 
3. Open the newly copied `KU_YYYY-MM-DD.pptx` file using the `powerpoint-mcp_manage_presentation_tool`. **Do not modify the original template**!
4. **Clarification Check:** While analyzing the user-provided PDF, if any portion or text of the liturgy is unclear or seems missing, **ask the user to verify** before creating the slide.
5. **Maintain Formatting:** Maintain formatting for each slide; do not alter any existing formatting (e.g., bold, italic, underline, size, etc.) of the original template slides unless explicitly instructed.

## 2. Generating Contents

For each section in the liturgy, identify the closest matching template layout or duplicate an existing template slide that fits the content type. If using existing slides, use `manage_slide` to copy and move them into the correct place.

### Sections
Section slides contain only the section title. These slides are usually hidden in the final presentation and used merely as reference markers. Duplicate an existing section reference slide in the template.

### Songs
- **Lyrics Splitting**: Split song lyrics into **2 to 5 lines maximum** per slide, depending on the textbox size in the template (larger text boxes support 5 lines, smaller support 2). Split the lyrics into multiple lines if needed to fit the template.
- **Song Structure**: For songs with multiple verses and an interspersed chorus/reff, create separate repeated slides for the chorus following each verse (e.g. verse 1 -> chorus -> verse 2 -> chorus).
- **Song Title slide**: Usually contains the title and source/creator. Prefer the source; if not exist, show the creator.
- **Tithe Songs (Persembahan)**: For offering/tithe songs, you must find and duplicate the special template slide that includes the **QR Code**.

### Scriptures
- The scripture text must be in Indonesian using the **"Terjemahan Baru (TB)"** translation as written in the user's source PDF.
- **One Verse Per Slide**: Split scriptures so that **one slide contains only one verse**.
- **Multi-slide Verses**: If a single verse is too long and must span multiple slides, attach an ellipsis `...` at the end of the first slide and another `...` at the start of the next slide to indicate continuation.
- **Formatting**: Include a **superscripted** verse number at the start of the verse text (e.g., `<sup>1</sup> In the beginning...`). Include the verse citation/source at the bottom or end of the verse (e.g., `Kejadian 1:1 (TB)`).

### Liturgy (Responsive Reading)
- Liturgy sections involve readings assigned to specific groups or individuals.
- You **must** indicate the speaker by **underlining** their designation. For example: <u>Liturgos</u>, <u>Jemaat</u>, or <u>Semua</u>. You can apply HTML-style `<u>` tags if using the `populate_placeholder` skill.

### Other Items ("Pengakuan Iman Rasuli")
- Simply duplicate the existing slides from the template for items like "Pengakuan Iman Rasuli." Do not alter their contents.
- General rule: When specific liturgy pieces (like Apostle's Creed) repeatedly occur, rely on the pre-existing slides within the template without rebuilding them.

## General Reminders
- Prioritize using predefined layouts if available using the `add_slide_with_layout` tool. However, if standard Slide Master layouts are missing or show up as "Unknown Layout", duplicate existing slides that match the required pattern block and then use the `populate_placeholder` tool to swap out text.
