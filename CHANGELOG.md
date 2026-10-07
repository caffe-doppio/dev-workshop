# Changelog

![TLP:CLEAR](assets/badges-tlp/tlp-clear.svg)

Corrections are logged here, never silently applied. Versioned documents are never overwritten: a new version sits next to the old one.

## 2026-10-07

### Support, `support/support_EN_v02.md`

| ID | Correction |
|----|------------|
| C-001 | v01 numbered the lab phases 5 to 7 without phases 1 to 4. v02 follows the timeline in `support/schemas/lab-flow.svg` |
| C-002 | v01 did not point to the participant workbook. v02 links each method to its wiki page |
| C-003 | Section 0: the clock table repeated `lab-flow.svg`. Removed; the timed run sits in the facilitator's speaker script |
| C-004 | Section 2: "What the gap looks like, by hub" replaced by "What digital evidence can establish" |
| C-005 | Section 5: each instrument gets a two-sentence description, an example snippet, and TLP labels shown as badges |
| C-006 | Section 6: storytelling presentation of the portal, screenshots, personas and live demo folded in `<details>` |
| C-007 | Sections 2 and 3: "What digital evidence can establish" and "Four evidence layers" tables replaced by schemas `evidence-establishes.svg` and `evidence-layers.svg` |

### Pitch

- Added `pitch/pitch-written_EN_v01.md`, written pitch for participants. "From the field" left to another session.

### Portal (`dev-miniluv`)

- `/.well-known/security.txt`: placeholder TODO removed, contact `dev@etdeuxmains.fr`, canonical URL on Scalingo.
