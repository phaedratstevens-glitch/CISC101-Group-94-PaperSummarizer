# Module 3 guardrails

## Change log

- Initial version

---

## Objectives

- **Evidence enforcement:** Ensure claims come only from provided text.
- **Section status messaging:** Provide clear messages for missing or short sections.
- **Hallucination mitigation:** Block unsupported statements.
- **Chunking logic:** Handle long papers deterministically while respecting PS2 constraints.

---

## Inputs

- **Per-section summaries:** text, status, notes.
- **Runtime config:** ps2_mode, evidence_mode, chunking flag, word_limit.

---

## Rules

- **Evidence mode strict:** If evidence_mode is “strict”
  - Only include claims, equations, and results present in the source text.
  - If insufficient detail, output the message
    - “The source text does not provide enough detail to summarize this section in strict evidence mode.”
- **Missing or empty sections:** Replace summary with
  - “Section skipped: no usable text was provided.”
- **Very short sections:** Prepend the note
  - “Section very short: summary may be incomplete.”
- **No outside facts:** Do not include content not present in the paper.
- **Terminology consistency:** Maintain mandated terms when applicable.
- **Chunking:** If chunking is active
  - Summarize per chunk, merge deterministically.
  - Add checks indicating chunking used.
- **PS2 enforcement:** In PS2 mode
  - Prevent any additional headings or sections beyond the four labels.
  - Track word count; if approaching limit, compress safely without losing factual accuracy.

---

## Outputs

- **Validated summaries:** Per-section text with guardrail messages applied.
- **Checks list:** Evidence mode notes, missing or short section flags, chunking indicators, PS2 compliance.
