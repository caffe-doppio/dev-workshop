# Borrowed from the Lab
## Coordination pitch, oral (EN)

![TLP:CLEAR](../assets/badges-tlp/tlp-clear.svg)

| Field | Value |
|-------|-------|
| Classification | TLP:CLEAR |
| Date | 2026-09-28 |
| Author | Sasha, Urgence Homophobie |
| Version | v01 |
| Audience | DFF InterHub coordination |
| Session | 2026-10-07, Amsterdam, 60 minutes |
| Target length | ~700 words, ~5 minutes |
| Sources | `src/DFF_InterHub_Session_Proposal.md`, `hub/utrecht-retreat/keynote/digital-evidence-methodology-slides-EN.md`, `_standups/`, `homelab/anef/notes/20260819_ANEF-workshop-pitch-5min_EN_v01.md` |
<!--| Typography | No em-dash, no en-dash |-->

---

## [0:00] Who we are, and why this is political

Hi everyone, I'm Sasha, from Urgence Homophobie in Marseille. We support LGBTQIA+ people in migration, and more and more, that means supporting them against software.

One sentence of history, because it explains why we do this. The network was born out of Cold War military research. In the eighties, with FidoNet and the bulletin boards, people got a taste of something close to an egalitarian utopia: anyone with a modem could be a node. Since then, digital infrastructure has turned into what Marx would call the base: the layer everything else stands on, and through which domination gets organised. For the people we work with, registries, portals and platforms are where the harm actually happens. Reclaiming the digital is how you stop simply enduring it.

## [1:00] The problem

That brings us to courts. More and more administrative decisions are taken, or blocked, by a platform. But the evidence of that rarely reaches a judge in a usable form. People arrive with a screenshot. Judges are not geeks, and they shouldn't have to be. Our job is not to impose a technical reading on the magistrate. It's to be precise and pedagogical at the same time: show where a right is blocked, and which administration is actually responsible, so the right body ends up as defendant. And there are no explicit admissibility criteria for this kind of evidence yet. We're partly writing the spec as we go.

## [2:00] From the field

A concrete case. ANEF is the French portal for foreign nationals. On one file, the portal refused access to the very procedure you use to correct your own data. The server said: allowed. The code running in the browser said: denied. The user saw: denied. Two bugs, two owners: a wrong value held by the prefecture, and blocking logic owned by the ministry's platform. Without the evidence chain, both complaints go to the same wrong address, and you lose months.

The same reasoning applies elsewhere. Prefecture appointment slots are widely reported to be scalped by bots, and people lose access to the queue itself. That's a rights problem too, and it leaves digital traces.

## [3:00] Honest limits

Two limits. First, we work passively only: our own sessions, our own files, no scanning, no probing. That keeps us on the right side of the law, but it means there are things we cannot see, and we don't claim them. Second, sometimes you stumble on a real vulnerability in the very service you're about to take to court. You don't exploit it, and you don't sit on it. You timestamp what you observed, you disclose it responsibly, and you keep the case about the rights, not the bug. Timestamping is what lets your evidence survive the patch.

## [3:40] The lab

Then we switch to practice, about two thirds of the session. I'm building a small fictional public service, straight out of Orwell, running on a real server: fake APIs, rather talkative logs, and at least one well-hidden bug. Participants open the browser console, find the calls that matter, export the traffic, fingerprint it, encrypt it for another group, and anchor it in time. Then groups exchange their evidence and verify it. One piece in circulation has been forged. Their job is to catch it.

Groups are mixed-hub by design: AI Hub folks tend to drive the tools, Digital Democracy Hub folks tend to argue what the evidence proves. Every group needs both.

No slides. Everything lives in an open Framagit repository: support, diagrams, templates and resources, including a short introduction to responsible OSINT.

## [4:20] What I need from coordination

A screen for live demos. Tables for small groups. Laptops where possible. Mixed-hub group assignment, which I'm happy to prepare from the list. Reliable Wi-Fi, since the lab runs online. And one alignment point: the proposal said 90 minutes, I'm planning for 60.

## [4:45] Close

The point isn't to turn lawyers into hackers. It's to make sure that when a system denies someone a right, the denial can be shown, understood, and sent to the right door. Thank you.

---

## Speaker notes

- If time runs short, cut the "slots" paragraph (the pattern is already carried by ANEF) and the OSINT sentence.
- "Widely reported to be scalped by bots" needs a public source [Clara Martot Barcy in Marsactu](https://marsactu.fr/a-marseille-des-etrangers-obliges-dacheter-des-rendez-vous-pour-etre-recus-en-prefecture/) before delivery.
Fallback wording: "the booking systems make scalping easy".
- Prefecture booking findings are TLP:AMBER+STRICT and not yet disclosed. Stay at pattern level: no mention of captcha type, request structure or slot inventory.
- ANEF case A is told as on 2026-08-19 (trusted audience). Case B (third-party file) and the `fprnsis` finding are out of scope for this pitch and for the public repository.
