# Frame: passive only

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** you observe what a normal browser receives in your own session, and you do nothing else.

[Back to the workbook](../README.md)

---

## Allowed

- Using the portal as any citizen would: clicking, navigating.
- Watching DevTools: Console, Network, Sources.
- Saving what your browser received (HAR, screenshots).

## Not allowed

- Changing an address by hand to reach another file, another citizen, another identifier.
- Trying other values, guessing hidden pages, repeating requests in bulk.
- Using any tool that sends requests the page would not have sent: scanners, scripts, request editors.

## Why

- **Law.** In France, accessing or staying in an automated data processing system without authorisation is an offence (Penal Code, art. 323-1). Most European countries have an equivalent. Observing your own session stays on the right side.
- **Evidence.** A finding made by tampering can be challenged, and can turn the case against the person who made it.
- **Trust.** The person whose file you document trusts you with it, not with their neighbours'.

## In the lab

The portal is fictional, and there is no real vulnerability in it. The rule still applies, because the habit is what you take home. If you catch yourself about to edit an address to "see what happens": stop, and write the idea in the custody log instead.

## See also

- [Evidence layers](frame-evidence-layers.md): what passive observation cannot see
- [Hidden bug and disclosure](frame-disclosure.md)
