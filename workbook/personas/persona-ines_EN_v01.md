# Persona: Ines Larkspur

![TLP:GREEN](../../assets/badges-tlp/tlp-green.svg)

| Field | Value |
|-------|-------|
| Session | DFF InterHub, Amsterdam, 2026-10-07 |
| Version | v01 |
| Classification | TLP:GREEN |
| Level | Challenge |
| Portal | <https://miniluv-workshop-hands-in.osc-fr1.scalingo.io/#/> |

[Back to the workbook](../README.md). All citizens are fictional. All data is synthetic.

---

## The citizen

| | |
|---|---|
| Citizen ID | `ML-0901-B` |
| Sector | Sector 5, Block D |

*Ines has asked to correct an error in their own file. The portal refuses. Ines wants to know whether to challenge it.*

## Your brief

- Reproduce what Ines sees, and record it as the screen shows it.
- Find out what the Ministry's servers actually answered.
- Is there a case against the portal? Saying "no" is a valid answer, if you can prove it.

---

## Setup (3 min)

1. Choose your [roles](../wiki/share-roles.md): Lab tech, Counsel, Custodian.
2. **Custodian**: open the [custody log](../wiki/share-custody-log.md). Line 1: time, group number, persona, who holds the laptop.
3. **Lab tech**: open a **private window**, then [DevTools](../wiki/browser-devtools.md) (`F12`, or `Cmd + Option + I` on macOS).
4. Go to the **Network** tab and keep the history:
   - Firefox: gear icon > **Persist Logs**.
   - Chrome: tick **Preserve log**.
5. Only now, open the portal: <https://miniluv-workshop-hands-in.osc-fr1.scalingo.io/#/>
6. Click **Identify yourself**, then choose **Ines Larkspur**.

> [!TIP]
> Glance at the **Console** tab from time to time. The Ministry talks there.

## Phase 5. Collect and seal (15 min)

**Screen.** On Ines's file page, copy the exact words of the **Record correction** box. Check the appointments page too.

**Wire.**

1. Network tab, filter **Fetch/XHR** (Chrome) or **XHR** (Firefox).
2. Click each request, one by one. Open **Preview** or **Response**. Unfold everything. How to read it: [Requests and JSON](../wiki/browser-requests-json.md).
3. Does the server's answer say the same thing as the screen, or something else? Both are possible.
4. For anything that matters, Custodian writes: request name, field, exact value, exact screen text.

**Counsel.** Screen and wire: same story, or not? Who decided what the screen shows? See [Evidence layers](../wiki/frame-evidence-layers.md).

**Going further** (fast groups): DevTools > **Sources** (Chrome) or **Debugger** (Firefox). Find the file that holds the portal's display rules. Can you find the rule behind what you saw?

**Seal.** In this order, one custody log line each:

1. Export the HAR, name it `groupN_ML-0901-B_YYYYMMDD-HHMM.har`: [Export a HAR](../wiki/browser-har.md).
2. Fingerprint it: [SHA-256](../wiki/seal-sha256.md).
3. Anchor it: [OpenTimestamps](../wiki/seal-opentimestamps.md). It will stay pending: normal.
4. Label it: [TLP](../wiki/share-tlp.md). Which colour would a real capture deserve?

Commands for your system: [Terminal cheat sheet](../wiki/terminal-cheatsheet.md).

## Phase 6. The hidden bug (8 min)

The portal sends more than it shows.

1. Go back over **every** response, and read each one **to the very end**.
2. Ask: is there anything here the citizen was never meant to see?
3. Found something? **Stop there.** Do not try other addresses or other citizens: [Passive only](../wiki/frame-passive-only.md).
4. Decide as a group, with [Hidden bug and disclosure](../wiki/frame-disclosure.md): what you do, who you tell, what you keep.
5. Custodian logs the decision. Counsel prepares two sentences.

## Phase 7. Hand-off and verification (12 min)

The facilitator tells you which group you send to. Guide: [age encryption](../wiki/seal-age.md).

**Send.**

1. Create your group key: `age-keygen -o group.key`. Post the `age1...` public key where everyone can see it. Never the `group.key` file.
2. Encrypt your HAR with the **receiving group's** public key.
3. Post the HAR's fingerprint (the one from phase 5) on the wall, or say it aloud: a **different channel** than the file.
4. Hand over the `.age` file the way the facilitator says (USB key, shared folder).

**Receive.**

1. Decrypt with your own `group.key`.
2. Fingerprint the decrypted file. Compare with the fingerprint the sender posted.
3. Verdict: **accept** or **reject**, and why, in one sentence. Custodian logs it.

---

## Stuck?

| Stuck on | Try |
|----------|-----|
| Anything | What does the Console say? |
| Network list is empty | Reload the page with DevTools open |
| Cannot find the right request | Open every request with `ML-0901-B` in its address |
| A command fails | [Terminal cheat sheet](../wiki/terminal-cheatsheet.md), "When something goes wrong" |
| Still stuck | Raise a hand: asking is part of the method |

## Counsel's sheet

Fill in before the debrief. One sentence each.

| Question | Your answer |
|----------|-------------|
| What did the screen say? | |
| What did the server answer? | |
| Who is responsible for the refusal? | |
| What can we **not** claim from this capture? | |
| What did you decide about the hidden bug? | |
