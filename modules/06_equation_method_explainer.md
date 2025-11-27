# Module 6 equation and method explainer

## Change log

- Initial version

---

## Purpose

- **Explain math and methods:** Generate concise explanations of equations, algorithms, and methodological steps found in the paper.
- **Audience adaptation:** Provide expert and lay explanations in general mode.

---

## Inputs

- **Paper text:** Sections containing equations or method descriptions.
- **Runtime config:** ps2_mode, evidence_mode, audience.

---

## Rules

- **Evidence strictness:** Only explain elements explicitly present in the text or equations shown.
- **No extrapolation:** Do not infer derivations or steps not provided.
- **PS2 restriction:** In PS2 mode, retain only terminology alignment and short section summaries; do not add extra explanatory sections.

---

## Steps

- **Identify elements:** Locate equations, algorithm blocks, or procedural steps.
- **Extract components:** Record variables, operations, and stated purposes.
- **Generate explanations:**
  - **Expert:** Concise technical explanation focusing on role, assumptions, and stated constraints.
  - **Lay:** Plain-language description of what the equation or method does and why it matters.
- **Terminology consistency:** Use the paper’s terms as written.

---

## Outputs

- **Explanation set:** Paired expert and lay explanations for each identified element in general mode.
- **PS2 compliance:** Confirmation that no extra sections were added in PS2 mode and terminology remained consistent.
