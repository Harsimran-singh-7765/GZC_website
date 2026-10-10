# SOLID STATELESS

A responsive, local-first NPTEL Solid State Physics revision website built with React + Vite.

## Included question bank
The site ships with the 80 question records extracted from the uploaded Markdown sources for Weeks 3–10 (10 questions per week). Original question wording, options, answer labels and revision notes are retained where present. When the source does not confirm an answer, the quiz marks it as unconfirmed instead of guessing.

## Features
- Week-wise question practice for Weeks 1–12
- Mixed/random practice across all loaded questions
- Import Markdown `.md` / `.markdown` / `.txt` files
- Add, edit, and delete questions
- Export the current bank to Markdown
- Correct-answer feedback and source notes
- Mathematical formula rendering with KaTeX (fractions, Greek letters, superscripts, subscripts, equations)
- Browser `localStorage` persistence; no backend required

## Run locally
```bash
npm install
npm run dev
```
Open the local URL printed by Vite.

## Markdown import
The importer is designed for common assignment layouts:
```md
# Week 11

## Q1. Question goes here?
**Options**
- (a) First option
- (b) Second option
- (c) Third option
- (d) Fourth option

**Correct option: (b)**
```
File names like `Week 11.md` set the fallback week. A `# Week 11` heading inside a file takes precedence. Existing questions are appended, not replaced.

## Formula formatting
Use standard Markdown math delimiters in new question files:
- Inline: `\\(E = mc^2\\)`
- Display: `\\[ E = mc^2 \\]`

The importer also strips common Pandoc `{=tex}` and backtick artefacts found in the uploaded Week 6–9 files.

## Important notes
- Data is saved in the current browser on the current device. Use **Export bank** to back it up.
- Some source questions explicitly note that an answer is unconfirmed or that no listed option matches. These are flagged rather than silently corrected.
