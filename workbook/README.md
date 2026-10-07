# Borrowed from the Lab: participant workbook

![TLP:CLEAR](../assets/badges-tlp/tlp-clear.svg)

| Field | Value |
|-------|-------|
| Session | DFF AI & Digital Democracy InterHub Gathering, Amsterdam, 2026-10-07 |
| Version | v01 |
| Classification | TLP:CLEAR (this page and the wiki); persona sheets are TLP:GREEN |
| Portal | <https://miniluv-workshop-hands-in.osc-fr1.scalingo.io/#/> |

*The Ministry of Love has opened a citizen portal. Citizens are being refused. Your lab has been asked to document it.*

Miniluv Citizen Services is fictional. Every citizen and every value in it is synthetic. Nothing here is a real administration.

---

## Before you come

- **One laptop per group** is enough, with **Firefox or Chrome**. A phone or a tablet will not do: no DevTools.
- On at least one laptop of the group, `age --version` must answer in a terminal. Not installed? [Terminal cheat sheet](wiki/terminal-cheatsheet.md#install-the-tools): install it before the session, some steps need admin rights.
- `ots` (OpenTimestamps) is optional: https://opentimestamps.org does the same without installing anything.

## How the lab works

1. Form a group of 3 to 5, mixing hubs. Pick [roles](wiki/share-roles.md): Lab tech, Counsel, Custodian.
2. Choose a persona below.
3. Follow your persona sheet, phase by phase. Every step links to the wiki page that explains it.

No technical experience is needed. Every group needs someone who reads code **and** someone who reads law.

## Choose your persona

| Persona | Level | Sheet |
|---------|-------|-------|
| Mira Ostrander | Starter | [persona-mira](personas/persona-mira_EN_v01.md) |
| Felix Quarry | Starter | [persona-felix](personas/persona-felix_EN_v01.md) |
| Noor Tallis | Two problems in one file | [persona-noor](personas/persona-noor_EN_v01.md) |
| Ines Larkspur | Challenge | [persona-ines](personas/persona-ines_EN_v01.md) |

**One rule for the room:** together, the groups must cover **Mira or Noor** and **Felix or Noor**. With two groups, one can take Noor, or each group takes two personas. The facilitator checks before you start.

## Timeline

| Phase | Time | What you do |
|-------|------|-------------|
| 4. Demo | 3 min | Watch the facilitator on the big screen |
| 5. Collect and seal | 15 min | Reproduce, compare screen and server, export, fingerprint, anchor, log, label |
| 6. The hidden bug | 8 min | Read everything to the end, decide what to do |
| 7. Hand-off and verification | 12 min | Encrypt for another group, receive, check, give a verdict |
| Debrief | 7 min | Counsel speaks |

## Wiki

One page per notion, written for people who have never opened DevTools.

**Browser**

- [DevTools](wiki/browser-devtools.md): open it, Console, Network, Sources
- [Requests and JSON](wiki/browser-requests-json.md): what the server answers, and how to read it
- [Export a HAR](wiki/browser-har.md): record the session, and why the file is sensitive

**Seal**

- [SHA-256 fingerprint](wiki/seal-sha256.md): prove a file has not changed
- [OpenTimestamps](wiki/seal-opentimestamps.md): prove when it existed
- [age encryption](wiki/seal-age.md): only the recipient can read it

**Track and share**

- [TLP](wiki/share-tlp.md): who may receive what
- [Custody log](wiki/share-custody-log.md): who held it, when, and did what (template inside)
- [Roles](wiki/share-roles.md): Lab tech, Counsel, Custodian

**Frame**

- [Passive only](wiki/frame-passive-only.md): what you may and may not do
- [Evidence layers](wiki/frame-evidence-layers.md): screen, wire, code, correlation
- [Hidden bug and disclosure](wiki/frame-disclosure.md): found a flaw, now what

**Tools**

- [Terminal cheat sheet](wiki/terminal-cheatsheet.md): every command, for macOS, Linux and Windows

## Take it home

This workbook stays online after the session. The methods work on any portal, as long as you stay [passive](wiki/frame-passive-only.md) and in your own session.
