# Borrowed from the Lab
## Written pitch (EN)

![TLP:CLEAR](../assets/badges-tlp/tlp-clear.svg)

| Field | Value |
|-------|-------|
| Classification | TLP:CLEAR |
| Date | 2026-10-07 |
| Author | Sasha, Urgence Homophobie |
| Version | v01 |
| Audience | Gathering participants, DFF programme |
| Session | 2026-10-07, Amsterdam, 60 minutes |
| Target length | ~500 words |
| Sources | `pitch/pitch-coordination_EN_v01.md`, `support/support_EN_v02.md` |
| Scope | Field cases ("From the field") are left out: they belong to another session |

---

**Cybersecurity methods for evidence management in strategic litigation.**

### Why the digital is political

The network was born out of Cold War military research. In the eighties, FidoNet and the bulletin boards offered a glimpse of an egalitarian network, where anyone with a modem could be a node. Since then, digital infrastructure has become the base on which everything else stands, and through which domination is organised.

At Urgence Homophobie, in Marseille, we support LGBTQIA+ people in migration. For them, registries, portals and platforms are where the harm actually happens: a refused correction, an appointment that never appears, a file that says no without saying why. Reclaiming the digital means documenting, proving and contesting it.

### The problem

More and more administrative decisions are taken, or blocked, by a platform. What reaches the judge is usually a screenshot: no checkable date, no trace of what the system actually answered, and nothing that says who is responsible.

Judges are not geeks, and they should not have to be. Our job is to be technical and pedagogical at the same time: show where a right is blocked and which administration is responsible, so the right body ends up as defendant. There are no explicit admissibility criteria for this kind of evidence yet. We are partly writing the spec as we go.

### What we borrow from the lab

Cybersecurity practitioners have long handled exactly this kind of material. We hand over five of their methods, reframed for legal practice:

- **Traffic Light Protocol**: who may receive what, across a coalition.
- **SHA-256 fingerprints**: proof that a file has not changed by a single byte.
- **OpenTimestamps**: proof that it existed at a given time, without disclosing its content.
- **age encryption**: only the intended recipient can read it.
- **Chain of custody**: who held it, when, and what they did.

Each one is read through three questions: what problem does it solve, how do you apply it, and what does it look like before a judge. And each one comes with its limits: we work passively, in our own sessions only, and we say what we cannot see.

### The lab

Two thirds of the session is hands-on. Miniluv Citizen Services, a fictional portal of Orwell's Ministry of Love, runs on a real server. Its citizens are being refused. In mixed-hub groups of lab tech, counsel and custodian, you open the browser's developer tools, compare what the screen says with what the server answered, seal the evidence, and hand it to another group, who must verify it before trusting it. Somewhere, the portal also shows more than it should. What you do about that is part of the exercise.

No technical experience is needed. Every group needs someone who reads code and someone who reads law.

### What you leave with

No slides. Everything lives in an open repository: support, participant workbook, wiki and templates, to reuse in your own cases.

The point is not to turn lawyers into hackers. It is to make sure that when a system denies someone a right, the denial can be shown, understood, and sent to the right door.

<https://framagit.org/caffe-doppio/gathering-lab>
