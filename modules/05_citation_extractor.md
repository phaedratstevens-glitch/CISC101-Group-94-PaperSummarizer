# Module 5 citation and reference extractor

## Change log

- Initial version

---

## Purpose

- **Extract references:** Identify in-text citations and reference list entries from the provided paper text.
- **Map citations:** Link in-text markers to bibliography entries when possible.
- **Support summaries:** Provide citation context for expert and glossary sections in general mode only.

---

## Inputs

- **Paper text:** Full text including references section if present.
- **Runtime config:** ps2_mode, evidence_mode.

---

## Rules

- **PS2 restriction:** In PS2 mode, do not include citations or references in the final output; use extraction only for internal checks.
- **Evidence alignment:** Only record citations that appear in the provided text.
- **No fabrication:** Do not infer or create missing bibliographic data.

---

## Steps

- **Detect citation patterns:** Identify bracketed numbers, author-year formats, or footnotes.
- **Extract reference entries:** Parse the references section into structured fields
  - **Authors:** List in provided order
  - **Year:** As stated
  - **Title:** Exact title
  - **Venue:** Journal or conference
  - **Identifiers:** DOI, arXiv, or URL if present in text
- **Map in-text to entries:** Create a lookup from citation markers to extracted entries.
- **Produce context:** Summarize what each cited work contributes, using only text explicitly stated.

---

## Outputs

- **Citation registry:** Structured list of citations and their mapped entries.
- **Context notes:** Brief factual notes per citation drawn from the paper text.
- **Compliance flag:** Confirmation that no citations were rendered in PS2 outputs.
