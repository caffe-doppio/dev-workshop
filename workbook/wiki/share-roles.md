# Share: roles in the group

![TLP:CLEAR](../../assets/badges-tlp/tlp-clear.svg)

> **In one sentence:** three roles, so that someone runs the tools, someone says what it proves, and someone keeps track.

[Back to the workbook](../README.md)

---

## The three roles

| Role | Does | Asks |
|------|------|------|
| **Lab tech** | Runs the browser and the terminal | "What exactly do I click or type?" |
| **Counsel** | Says what the evidence proves, and what it does not | "Would a judge understand this sentence?" |
| **Custodian** | Keeps the [custody log](share-custody-log.md). Nobody touches a piece without a line | "Who did what, when?" |

With more than three people: two Lab techs (one browser, one terminal), or a second Counsel who argues the other side.

**No technical experience?** Counsel and Custodian are made for you. The Lab tech needs you: the tool does not decide what matters.

## Who does what, phase by phase

| Phase | Lab tech | Counsel | Custodian |
|-------|----------|---------|-----------|
| Setup | Opens private window and DevTools | Reads the brief aloud | Opens the log, line 1 |
| Collect and seal | Reproduces, finds the requests, exports, fingerprints, anchors | Compares screen and server, decides what counts | Logs each step, sets the TLP label with the group |
| Hidden bug | Reads every response to the end | Frames the decision | Logs the decision |
| Hand-off | Keys, encryption, decryption, fingerprint check | Gives the verdict in one sentence | Logs what was sent and received |

## Swap

Halfway through, swap Lab tech and Counsel if the group agrees. Lawyers driving DevTools and technicians drafting sentences both learn the most.

## See also

- [Custody log](share-custody-log.md)
- [Evidence layers](frame-evidence-layers.md)
