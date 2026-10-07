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
| C-008 | Section 7: decryption wrote to `-o evidence.har`. `age` overwrites an existing file without warning, so a received piece could replace one's own capture. Now `-o received.har`, as in the wiki |
| C-009 | Section 7: `ots verify` was given as the check "once the anchor is confirmed". It needs a local Bitcoin node; the website is now named as the way to verify |

### Workbook

- `wiki/terminal-cheatsheet.md`: `pip3 install opentimestamps-client` fails on recent macOS (Homebrew Python) and Debian/Ubuntu with `externally-managed-environment`. Replaced by `brew install opentimestamps-client` (macOS) and `pipx` (Linux). Windows: no tested path, the website is given instead.
- `wiki/terminal-cheatsheet.md`: added that `age` has no web fallback, that `-o` overwrites without warning, and that Windows prints fingerprints in capitals.
- `wiki/seal-sha256.md`: the page promised a comparison done by the computer "below" and gave none. Commands added for macOS, Linux and Windows.
- `wiki/seal-age.md`: overwrite with `-o` added to common mistakes.
- `README.md`: new "Before you come" section: one laptop per group, Firefox or Chrome, `age` on at least one laptop, `ots` optional.
- Added `after-the-workshop.md` and the GitHub issue form `.github/ISSUE_TEMPLATE/after-the-workshop.yml`: the discussion questions, to answer after the session by issue or pull request. Public: patterns, not names.

### Pitch

- Added `pitch/pitch-written_EN_v01.md`, written pitch for participants. "From the field" left to another session.

### Portal (`dev-miniluv`)

- `/.well-known/security.txt`: placeholder TODO removed, contact `dev@etdeuxmains.fr`, canonical URL on Scalingo.
