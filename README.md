# Borrowed from the Lab

![TLP:CLEAR](assets/badges-tlp/tlp-clear.svg)

Cybersecurity methods for evidence management in strategic litigation.

Participatory workshop,
[DFF AI & Digital Democracy InterHub Gathering](https://digitalfreedomfund.org/community-programme/strategic-litigation-hubs/),
Amsterdam,
2026-10-07
60 minutes.

Facilitation: Sasha, Urgence Homophobie.

## About

Litigators increasingly build cases on digital evidence: screenshots, platform notices, portal refusals, model outputs.

Cybersecurity practitioners have long-standing methods to handle exactly that kind of material.

This repository hands some of them over, reframed for legal practice: the Traffic Light Protocol, SHA-256 fingerprints, OpenTimestamps anchors, age encryption and chain of custody.

> [!TIP]
> There are no slides. This repository is the support: participants read it during the session and keep it afterwards.
> The hands-on part runs on a fictional, Orwellian citizen portal built for the occasion.
> No real case data is published here.

## Find this repository

![QR code to https://github.com/caffe-doppio/dev-workshop](assets/qr/repo-dev-workshop.svg)

<https://framagit.org/caffe-doppio/gathering-lab>
<!--Pour faire beau-->
<https://github.com/caffe-doppio/dev-workshop>

Participants: start with [`workbook/README.md`](workbook/README.md).
Workshop presentation for the organisers: [`support/support_EN_v02.md`](support/support_EN_v02.md).

## Status

Work in progress. Materials are being prepared for the session.
<!-- N'est pas mettre des répertoires et fichiers .gitignored, sauf dev/ -->
## Arborescence

- [`README.md`](README.md)
- [`CHANGELOG.md`](CHANGELOG.md): corrections, logged never silently applied
- [`.gitignore`](.gitignore)
- [`.gitattributes`](.gitattributes): evidence files keep their exact bytes
- [`assets/`](assets/)
  - [`badges-tlp/`](assets/badges-tlp/): TLP 2.0 badges (clear, green, amber, amber-strict, red)
  - [`qr/repo-gathering-lab.svg`](assets/qr/repo-gathering-lab.svg): QR code to the Framagit repository
  - [`qr/repo-dev-workshop.svg`](assets/qr/repo-dev-workshop.svg): QR code to the GitHub mirror
- [`src/`](src/)
  - [`DFF_InterHub_Session_Proposal.md`](src/DFF_InterHub_Session_Proposal.md): validated proposal, 90 min format, kept as is
- [`pitch/`](pitch/)
  - [`pitch-coordination_EN_v01.md`](pitch/pitch-coordination_EN_v01.md): oral pitch for the coordination call
- [`support/`](support/)
  - [`support_EN_v02.md`](support/support_EN_v02.md): workshop presentation for the organisers
  - [`schemas/`](support/schemas/)
    - [`lab-flow.svg`](support/schemas/lab-flow.svg): 60 minute timeline
    - [`digital-history.svg`](support/schemas/digital-history.svg): why the digital is political
    - [`right-defendant.svg`](support/schemas/right-defendant.svg): server, browser, user: two bugs, two owners
    - [`evidence-establishes.svg`](support/schemas/evidence-establishes.svg): what digital evidence can establish
    - [`evidence-layers.svg`](support/schemas/evidence-layers.svg): four evidence layers, cheapest first
    - [`evidence-circuit.svg`](support/schemas/evidence-circuit.svg): collect, seal, hand off, verify
  - `screenshots/`: Miniluv portal screenshots
- [`workbook/`](workbook/): participant material, **start here during the lab**
  - [`README.md`](workbook/README.md): how the lab works, persona choice, wiki index
  - [`personas/`](workbook/personas/): one sheet per fictional citizen, TLP:GREEN
  - [`wiki/`](workbook/wiki/): one page per notion (browser, seal, share, frame, terminal)
- [`lab/`](lab/): fictional citizen portal, prod (after the session)
- [`facilitation/`](facilitation/): timed runbook, empty for now
- [`resources/`](resources/): responsible OSINT, further reading, empty for now
- `dev/miniluv/`: fictional citizen portal, dev and preprod. Source at <https://github.com/caffe-doppio/dev-miniluv>; the portal runs at <https://miniluv-workshop-hands-in.osc-fr1.scalingo.io/#/>
  - `README.md`: how to run it locally
  - `specs/SPEC-miniluv_v01.md`: personas, endpoints, scenarios, fixture plan
  - `site/`: Vue + Fastify portal, Docker, static JSON API
  - `fixtures/`: synthetic HAR and pre-anchored `.ots`
  - `templates/`: custody log, install checklist, empty for now

## Planned

Not created yet, listed for orientation only:

- `lab/miniluv/` : promotion of `dev/miniluv/` after the session
- `lab/templates/` : custody log (YAML and printable), install checklist (age, OpenTimestamps client)
- `facilitation/runbook.md` : timed runbook
- `resources/osint.md` : responsible OSINT introduction

<!-- ## Conventions

- No em-dash, no en-dash in produced content.
- Versioned documents are never overwritten: v01 is kept alongside v02.
- All dev/ material is synthetic and TLP:CLEAR. No real case data.
- Some stuff in lab/, resources/ and facilitation/ may be TLP:GREEN.

## Licence

To be decided.
