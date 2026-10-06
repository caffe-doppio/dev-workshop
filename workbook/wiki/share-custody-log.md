# Share: custody log

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** a running record of who held each piece, when, and what they did with it.

[Back to the workbook](../README.md)

---

## Why

A judge may ask: "How do I know this file is the one captured that day, and that nobody touched it?" The custody log is the answer, line by line. It follows the logic of ISO/IEC 27037: identify, collect, acquire, preserve.

What it does not prove: that the log itself is honest. Its strength comes from being written **at the moment**, and checked against fingerprints and anchors.

## Rules

- The **Custodian** writes it. Nobody touches a piece without a line.
- One line per action. Never erase: a mistake is corrected by a new line.
- Times in 24h format, with the time zone the first time (`CEST`).
- Fingerprints are copied, not retyped.

## Template

Copy this table into a text file, a shared pad, or onto paper.

| # | Time | Who | Action | Piece | SHA-256 (first 8 ... last 8) | TLP | Note |
|---|------|-----|--------|-------|------------------------------|-----|------|
| 1 | | | Start: group, roles, laptop owner | | | | |
| 2 | | | Captured | | | | |
| 3 | | | Fingerprinted | | | | |
| 4 | | | Anchored (`.ots` created, pending) | | | | |
| 5 | | | Labelled | | | | |
| 6 | | | Encrypted for group N | | | | |
| 7 | | | Received from group N | | | | |
| 8 | | | Decrypted, fingerprint compared: same / different | | | | |
| 9 | | | Verdict: accept / reject, and why | | | | |

Add lines for anything else that happens, especially a decision about a bug ([disclosure](frame-disclosure.md)).

## A good line

```text
4 | 15:42 CEST | Amira (Lab tech) | Anchored | group2_P-0000_20261007-1538.har | 3f2a9c0e ... 2f6b9e0d | AMBER | ots stamp, pending
```

## See also

- [Roles](share-roles.md)
- [SHA-256 fingerprint](seal-sha256.md)
- [TLP](share-tlp.md)
