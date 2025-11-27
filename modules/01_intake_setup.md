/modules/01_intake_setup.md

# Module 1 intake and setup

## Change log

- Initial version

---

## Objectives

- **Normalize sections:** Map user-provided section names to canonical labels and order.
- **Detect issues:** Identify missing, empty, or very short sections.
- **Apply constraints:** Enforce PS2 mode when applicable and set context, length, and audience parameters.

---

## Inputs

- **Paper text:** Full text or per-section text blocks.
- **Section list:** Ordered list of target sections.
- **Audience:** Intended audience string.
- **Flags:** evidence_mode, summary_level, word_limit, ps2_mode.

---

## Steps

- **Canonicalization:** Normalize section names to exact strings
  - Introduction
  - Architecture or Model
  - Training or Experimental Setup
  - Results
- **Ordering:** Ensure the sections are in the canonical PS2 order when ps2_mode is active.
- **Presence check:** For each section, locate its text in the paper using headings, keywords, and structural cues.
- **Length check:** Mark sections with fewer than 50 words as very short.
- **Emptiness:** Mark sections with no extractable text as missing.
- **Constraints:** Set word limits
  - PS2 mode → maximum 200 words total across all four outputs.
  - General mode → respect user word limit if provided; otherwise default to concise output.
- **Audience mapping:** Store audience to condition phrasing for general mode; do not change terms mandated by PS2.
- **Terminology lock:** Ensure use of self-attention, multi-head attention, Transformer, positional encoding when summarizing the specified paper.
- **Context window:** If paper exceeds capacity, set chunking flag and record chunk strategy.

---

## Outputs

- **Section registry:** For each canonical section, store
  - status: present, missing, empty, or very short
  - extracted_text: the raw text block
  - notes: detection details
- **Runtime config:** ps2_mode, evidence_mode, summary_level, audience, word_limit, chunking flag.
- **Warnings:** List of missing or short sections for downstream modules.
