# Seal: OpenTimestamps anchor

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** an anchor proves that a fingerprint already existed at a given time, by writing it into a public record nobody can rewrite afterwards.

[Back to the workbook](../README.md)

---

## What it proves, and what it does not

| Proves | Does not prove |
|--------|----------------|
| This exact file existed no later than the anchor time | What the file means or whether it is true |
| The evidence predates a later event, for example a patch of the portal | Who created it |

> [!NOTE]
> OpenTimestamps is not a qualified electronic timestamp under eIDAS (Regulation (EU) No 910/2014, art. 41). A judge does not presume its value: counsel has to explain it.

## Your file stays with you

Only the [fingerprint](seal-sha256.md) leaves your computer, never the file. You can prove the file existed without revealing what is in it.

## Commands

Install: see [Terminal cheat sheet](terminal-cheatsheet.md).

```sh
ots stamp evidence.har          # creates evidence.har.ots next to the file
ots info evidence.har.ots       # shows what the anchor contains
ots upgrade evidence.har.ots    # later: completes the anchor once confirmed
ots verify evidence.har.ots     # checks the file against the anchor
```

Keep the `.ots` file **next to** the evidence and log it in the [custody log](share-custody-log.md). Lose the `.ots`, lose the proof.

## Pending is normal

Right after `ots stamp`, the anchor is **pending**: it has been sent to public calendar servers, and will be written into the Bitcoin blockchain within a few hours. During the lab, your anchors will stay pending. That is expected.

To see a confirmed anchor, the facilitator will show one made days before the session.

## Without a terminal

The website https://opentimestamps.org lets you drop a file and get the `.ots` back. The fingerprint is computed in your browser; the file is not uploaded.

## See also

- [SHA-256 fingerprint](seal-sha256.md)
- [Hidden bug and disclosure](frame-disclosure.md): why timestamping lets evidence survive a patch
