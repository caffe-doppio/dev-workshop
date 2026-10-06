# Frame: hidden bug and disclosure

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** you find a flaw in the very service you want to take to court; you do not exploit it, you do not sit on it.

[Back to the workbook](../README.md)

---

## The dilemma

- Keep it quiet, and other users stay exposed.
- Publish it, and the operator patches it: the trace may vanish before the hearing.
- Use it, and you become the offender ([passive only](frame-passive-only.md)).

## The path

1. **Stop.** Do not try anything more to "confirm" it.
2. **Record what you already observed**: HAR, [fingerprint](seal-sha256.md), [anchor](seal-opentimestamps.md). Timestamping is what lets your evidence survive the patch.
3. **Log it** in the [custody log](share-custody-log.md): what, when, who saw it, and the decision.
4. **Label it**: a flaw is usually [TLP:AMBER or stricter](share-tlp.md) until fixed.
5. **Disclose responsibly** to the operator: the `security.txt` file of a site (`/.well-known/security.txt`) says who to contact. In France, the national authority (ANSSI) can also receive reports.
6. **Keep the case about the rights**, not the bug.

## Questions for the group

- Who is exposed by this flaw, and to whom?
- What do we keep, and with which label?
- Who do we tell, by when?
- Does it belong in the case at all? If yes, how does counsel say it in two sentences?

## In the lab

Write the group's answer in the custody log. Counsel will present it at the debrief.

## See also

- [Passive only](frame-passive-only.md)
- [OpenTimestamps](seal-opentimestamps.md)
