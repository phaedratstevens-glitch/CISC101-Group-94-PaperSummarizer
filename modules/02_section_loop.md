# Module 2 section loop

## Change log

- Initial version  
- 2025-11-27: Added `summary_level` variable and short vs detailed section behavior.
---

## Objectives

- **Process sections:** Extract and summarize each section in order.
- **Control detail:** Use summary_level to produce short or detailed summaries.
- **Respect PS2:** In PS2 mode, produce only the compact summaries needed for the four outputs.

---

## Inputs

- **Section registry:** statuses, extracted_text, notes.
- **Runtime config:** ps2_mode, evidence_mode, summary_level, audience, word_limit.

---

## Variables

- **summary_level:** Allowed values are “short” or “detailed”.
- **section_output:** Structured summary per section.

---

## Loop steps

- **Iterate ordered sections:** Process Introduction; Architecture or Model; Training or Experimental Setup; Results.
- **Extraction:** Use extracted_text from registry; do not fetch outside content.
- **Evidence mode check:** If strict and text is insufficient, defer to guardrails messaging.
- **Summarization in short mode:**
  - Produce one to two sentences.
  - Avoid bullets, quotes, and citations.
  - Use mandated terminology when applicable.
- **Summarization in detailed mode:**
  - Produce a short paragraph followed by a bullet list of three to five key points.
  - Keep points factual and sourced from the provided text.
- **PS2 enforcement:** If ps2_mode is active
  - Force summary_level to short.
  - Limit each section to one to two sentences.
  - Track cumulative word count to not exceed 200 words total.
- **Unknowns:** If details are absent in text, include “unspecified” within the summary.
- **Store result:** Save section_output with text and any notes.

---

## Outputs

- **Per-section summaries:** Structured objects with
  - text: the summary produced
  - status: normal, missing, empty, very short
  - notes: evidence mode or unknowns
- **Cumulative metrics:** Word count and compliance flags for PS2 mode.
