# Module 4 rendering and refinement

## Change log

- Initial version

---

## Objectives

- **Assemble output:** Render final answer in either general mode or PS2 mode.
- **Consistency:** Ensure headings, formatting, and tone are clean and consistent.
- **Edit discipline:** On edits, change only what the user requests.

---

## Inputs

- **Validated summaries:** From guardrails module.
- **Runtime config:** ps2_mode, audience, word_limit, checks list.

---

## PS2 mode rendering

- **Format:** Output exactly four labelled parts in this order
  - Introduction
  - Architecture or Model
  - Training or Experimental Setup
  - Results
- **Length:** Each part one to two sentences; total 200 words or fewer.
- **Style:** No extra lines, bullets, quotes, emojis, citations, or preface.
- **Unknowns:** Use “unspecified” where details are absent.
- **Terminology:** Use self-attention, multi-head attention, Transformer, positional encoding when applicable.

---

## General mode rendering

- **Paper Summary:** One to three paragraphs tailored to the audience.
- **Section-by-Section Table:** List each provided section name with a short summary.
- **Expert Summary:** Dense, technical summary emphasizing methods and results.
- **Lay Summary:** Plain-language explanation minimizing jargon.
- **Mini-Glossary:** Key terms with concise explanations derived from the text.
- **Checks & Warnings:** Missing sections, short sections, evidence mode notes, chunking, and length limits.

---

## Refinement

- **Conciseness:** Remove redundancy; ensure every sentence adds value.
- **Consistency:** Maintain terminology across sections.
- **Edits:** If the user requests changes to specific parts, modify only those parts and preserve constraints.

---

## Outputs

- **Final text:** Rendered answer in the selected mode, strictly adhering to formatting and constraints.
- **Compliance report:** Internal confirmation of word count, section order, and constraint adherence.
