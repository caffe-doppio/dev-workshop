# Seal: SHA-256 fingerprint

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** a fingerprint is a short code computed from a file; change one byte of the file and the code changes completely.

[Back to the workbook](../README.md)

---

## What it proves, and what it does not

| Proves | Does not prove |
|--------|----------------|
| The file has not changed by a single byte since the fingerprint was taken | Who made the file |
| Two copies are identical | When it was made (that is [OpenTimestamps](seal-opentimestamps.md)) |
| | What the file means |

## What it looks like

64 characters, letters `a` to `f` and digits:

```text
3f2a9c0e7b1d4a8e6f5c2b9a0d7e3c1f8b4a6e2d9c0f7a3b5e1d8c4a2f6b9e0d
```

Nobody compares 64 characters by eye under time pressure. Compare the **first 8 and last 8** aloud, then let the computer compare the rest (below).

## Compute it

Open a terminal in the folder where the file is ([how](terminal-cheatsheet.md)).

| System | Command |
|--------|---------|
| macOS | `shasum -a 256 evidence.har` |
| Linux | `sha256sum evidence.har` |
| Windows, PowerShell | `Get-FileHash .\evidence.har -Algorithm SHA256` |
| Windows, cmd | `certutil -hashfile evidence.har SHA256` |

Copy the result into the [custody log](share-custody-log.md), with the time.

## Check a file you received

1. Get the expected fingerprint by a **different channel** than the file (posted on the wall, said aloud, written on paper).
2. Let the computer compare it with the file you received. Replace `EXPECTED` with the 64 characters:

| System | Command | Same file | Different file |
|--------|---------|-----------|----------------|
| macOS | `echo "EXPECTED  received.har" \| shasum -a 256 -c` | `received.har: OK` | `received.har: FAILED` |
| Linux | `echo "EXPECTED  received.har" \| sha256sum -c` | `received.har: OK` | `received.har: FAILED` |
| Windows, PowerShell | `(Get-FileHash .\received.har).Hash -eq "EXPECTED"` | `True` | `False` |

Two spaces between the fingerprint and the file name. Capitals or lower case do not matter: Windows prints capitals, macOS and Linux lower case.

3. Same? The file is the one that was fingerprinted. Different? **Reject it**, whatever it contains.

> [!TIP]
> Why a different channel: if someone can swap the file, they can also swap a fingerprint sent next to it.

## Try it

Make a copy of any text file, change one letter, fingerprint both. Nothing in common.

## See also

- [OpenTimestamps](seal-opentimestamps.md)
- [age encryption](seal-age.md)
