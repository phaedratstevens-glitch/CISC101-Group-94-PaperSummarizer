# CISC101 Group 94 – Paper Summarizer

This repo contains our Research Paper Summarizer project for CISC 101.

## Files

- `system_prompt.md` — Full system prompt for the summarizer.
- `modules/01_intake_setup.md` — Normalizes inputs, sets PS2 mode, and checks section presence/length.
- `modules/02_section_loop.md` — Loops over sections and summarizes them with `summary_level = "short"` or `"detailed"`.
- `modules/03_guardrails.md` — Enforces strict evidence mode and standardized warnings for missing/short sections.
- `modules/04_rendering_refinement.md` — Renders final outputs (paper summary, expert/lay, glossary, checks).
- `modules/05_citation_extractor.md` — Extracts citations and references from the paper text.
- `modules/06_equation_method_explainer.md` — Explains equations and methods for expert and lay audiences.
