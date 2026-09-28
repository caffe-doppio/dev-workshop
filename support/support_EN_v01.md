# Borrowed from the Lab
## Workshop support

| Field | Value |
|-------|-------|
| Session | DFF AI & Digital Democracy InterHub Gathering, Amsterdam, 2026-10-07 |
| Duration | 60 minutes: 18 framing, 42 hands-on |
| Facilitation | Sasha, Urgence Homophobie |
| Version | v01 |

> Cybersecurity methods for evidence management in strategic litigation.

---

## 0. How this session works

![60 minutes in the lab](schemas/lab-flow.svg)

- No slides. This repository is the support, and you can take it home.
- Mixed-hub groups. Every group holds three roles:
  - **Lab tech**: runs the instruments.
  - **Counsel**: says what the evidence proves, and what it does not.
  - **Custodian**: keeps the custody log, and nobody touches a piece without writing it down.
- Every method is read through three questions:
  - What problem does it solve?
  - How do you apply it?
  - What does it look like before a judge?

---

## 1. Why the digital is political

![Why the digital is political](schemas/digital-history.svg)

- The network was born out of Cold War military research.
- In the eighties, FidoNet and the bulletin boards gave a taste of an egalitarian utopia: anyone with a modem could be a node.
- Since then, digital infrastructure has become the base, in Marx's sense: the layer everything else stands on, and through which domination is organised.
- For LGBTQIA+ people in migration, registries, portals and platforms are where the harm actually happens.
- Reclaiming the digital means documenting, proving and contesting. It is how you stop simply enduring it.

---

## 2. The problem: digital evidence before an administrative judge

- More and more administrative decisions are taken, or blocked, by a platform.
- What usually reaches the judge: a screenshot.
- Judges are not geeks, and they should not have to be.
- Our role: be technical and pedagogical at the same time, without imposing a reading on the magistrate.
- The goal: show **where** a right is blocked, and **which administration** is responsible, so the right body ends up as defendant.
- In the proceedings we work on, there are no explicit admissibility criteria for this kind of evidence yet. We are partly writing the spec as we go.

---

## 3. From the field

![Pointing at the right defendant](schemas/right-defendant.svg)

- A national online portal refused access to the very procedure used to correct one's own data.
- The server said: allowed. The code in the browser said: denied. The user saw: denied.
- Two bugs, two owners: a wrong data value held by one body, a blocking rule owned by another.
- Four evidence layers, cheapest first:
  - **Screen**: what a non-technical person can read.
  - **Wire**: the HAR capture, what the server actually answered.
  - **Code**: the rule that produced the refusal.
  - **Correlation**: server answer matched against the rule.
- Any layer alone fails. Together they close the chain.
- The same reasoning applies to online appointment booking, where people can lose access to the queue itself.

> [!NOTE]
> Cases are presented orally. Only patterns are published here, pending coordinated disclosure.

---

## 4. Honest limits

- **Passive only.** Your own session, your own file, what a normal browser loads. No scanning, no probing, no fuzzing. In France, unauthorised access to an automated data processing system is an offence (Penal Code, art. 323-1).
- **What passive cannot see.** Server-side logic, other users, other paths. Do not claim it.
- **One file is a finding, not a statistic.** Scope beyond the observed case stays a hypothesis.
- **A timestamp is not a presumption.** OpenTimestamps is not a qualified electronic timestamp under eIDAS (Regulation (EU) No 910/2014, art. 41). Its weight must be explained to the judge, it is not presumed.
- **The disclosure dilemma.** You find a vulnerability in the very service you want to take to court:
  - Do not exploit it.
  - Do not sit on it: users are exposed.
  - Timestamp what you observed, disclose it responsibly, keep the case about the rights, not the bug.
  - Timestamping is what lets your evidence survive the patch.

---

## 5. The instruments

### Traffic Light Protocol (TLP 2.0, FIRST)

| Label | Who may receive it |
|-------|--------------------|
| TLP:RED | Named recipients only, no further sharing |
| TLP:AMBER+STRICT | The recipient's organisation only |
| TLP:AMBER | The recipient's organisation and those who need to know to act on it |
| TLP:GREEN | The community, not public channels |
| TLP:CLEAR | Anyone |

- Label **every** piece and every document. Unlabelled means nobody knows who may see it.
- In a coalition: the label travels with the piece, not with the person.

### What each instrument proves, and what it does not

| Instrument | Proves | Does not prove |
|------------|--------|----------------|
| SHA-256 fingerprint | The file has not changed by a single byte | Who made it, or when |
| OpenTimestamps anchor | The fingerprint existed at a given time | What the file means |
| age encryption | Only the recipient can read it | Who sent it |
| Custody log | Who held it, when, and what they did | That the log itself is honest, unless it is checked |
| TLP label | Who may receive it | Anything about the content |

- OpenTimestamps sends only the fingerprint, never the file. You can prove existence without disclosing content.
- A new anchor stays "pending" until it is confirmed in the Bitcoin blockchain, usually a matter of hours.
- Chain of custody follows the logic of ISO/IEC 27037: identify, collect, acquire, preserve.

---

## 6. The lab: Miniluv Citizen Services

![Collect, seal, hand off, verify](schemas/evidence-circuit.svg)

*The Ministry of Love has opened a citizen portal. Citizens are being refused. Your lab has been asked to document it.*

### Phase 5. Collect and seal (15 min)

- Open DevTools **before** anything else. Network tab:
  - Firefox: tick **Persist Logs**.
  - Chrome: tick **Preserve log**.
- Reproduce the refusal.
- Find the call whose answer contradicts what the screen says.
- Export the HAR. Treat it as sensitive: in real life it holds session tokens and personal data.
- Fingerprint it, anchor it, write it in the custody log, label it TLP.

### Phase 6. The hidden bug (8 min)

- The portal shows more than it should. Somewhere.
- Found it? Decide as a group: what you do, who you tell, what you keep.
- Write the decision in the custody log. Counsel explains it in two sentences.

### Phase 7. Hand-off and verification (12 min)

- Generate your group key, post your public key (`age1...`) where everyone can see it.
- Encrypt your evidence for the next group, post its fingerprint in the room.
- Receive, decrypt, fingerprint again, compare with what was posted.
- Verdict: accept or reject. Trust nothing you receive until you have checked it.

---

## 7. Cheat sheet

```sh
# Fingerprint
shasum -a 256 evidence.har                        # macOS
sha256sum evidence.har                            # Linux
certutil -hashfile evidence.har SHA256            # Windows (cmd)
Get-FileHash .\evidence.har -Algorithm SHA256     # Windows (PowerShell)

# Anchor in time
ots stamp evidence.har                            # creates evidence.har.ots
ots verify evidence.har.ots                       # once the anchor is confirmed

# Encrypt for another group
age-keygen -o group.key                           # prints your public key: age1...
age -r age1... -o evidence.har.age evidence.har   # encrypt for the recipient's key
age -d -i group.key -o evidence.har evidence.har.age   # decrypt with your own key
```

---

## 8. Debrief

<details>
<summary>Open after phase 7</summary>

- Encryption protects confidentiality, not origin. Anyone holding your public key can encrypt a file for you.
- Integrity comes from the fingerprint, checked against a record that travelled through a different, trusted channel.
- Time comes from the anchor.
- Question for counsel: which of these would a judge understand, and how would you say it in one sentence?

</details>

---

## 9. Contribute

- Open an issue: a case type from your hub, a template, a translation, a correction.
- Corrections are logged, never silently applied.

---

## 10. Resources

- TLP 2.0: https://www.first.org/tlp/
- OpenTimestamps: https://opentimestamps.org
- age: https://github.com/FiloSottile/age
- ISO/IEC 27037:2012, guidelines for identification, collection, acquisition and preservation of digital evidence
- Regulation (EU) No 910/2014 (eIDAS), art. 41
- Responsible OSINT: see `resources/` (in preparation)
