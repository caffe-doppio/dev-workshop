# Borrowed from the Lab

![TLP:CLEAR](assets/badges-tlp/tlp-clear.svg)

Cybersecurity methods for evidence management in strategic litigation.

Participatory workshop, DFF AI & Digital Democracy InterHub Gathering, Amsterdam, 2026-10-07, 60 minutes.

Facilitation: Sasha, Urgence Homophobie.

## About

Litigators increasingly build cases on digital evidence: screenshots, platform notices, portal refusals, model outputs. Cybersecurity practitioners have long-standing methods to handle exactly that kind of material. This repository hands some of them over, reframed for legal practice: the Traffic Light Protocol, SHA-256 fingerprints, OpenTimestamps anchors, age encryption and chain of custody.

There are no slides. This repository is the support: participants read it during the session and keep it afterwards. The hands-on part runs on a fictional, Orwellian citizen portal built for the occasion. No real case data is published here.

Start with [`support/support_EN_v01.md`](support/support_EN_v01.md).

## Status

Work in progress. Materials are being prepared for the session.

## Arborescence

```text
workshop/
├── README.md
├── .gitignore
├── .gitattributes                          (evidence files keep their exact bytes)
├── assets/
│   └── badges-tlp/                         (TLP 2.0 badges: clear, green, amber, amber-strict, red)
├── src/
│   └── DFF_InterHub_Session_Proposal.md    (validated proposal, 90 min format, kept as is)
├── pitch/
│   └── pitch-coordination_EN_v01.md        (oral pitch for the coordination call)
├── support/
│   ├── support_EN_v01.md                   (workshop support, start here)
│   └── schemas/
│       ├── lab-flow.svg                    (60 minute timeline)
│       ├── digital-history.svg             (why the digital is political)
│       ├── right-defendant.svg             (server, browser, user: two bugs, two owners)
│       └── evidence-circuit.svg            (collect, seal, hand off, verify)
├── lab/
│   ├── miniluv/                            (fictional citizen portal)
│   │   └── specs/
│   │       └── BRIEF-claude-code_v01.md    (self-contained brief: specs and alpha landing page)
│   ├── fixtures/                           (synthetic HAR and pre-anchored .ots, empty for now)
│   └── templates/                          (custody log, install checklist, empty for now)
├── facilitation/                           (timed runbook, empty for now)
│   └── private/                            (gitignored: answer key, forged piece)
└── resources/                              (responsible OSINT, further reading, empty for now)
```

## Planned

Not created yet, listed for orientation only:

- `lab/miniluv/specs/SPEC-miniluv_v01.md` and `lab/miniluv/site/` : produced from the brief
- `lab/templates/` : custody log (YAML and printable), install checklist (age, OpenTimestamps client)
- `facilitation/runbook.md` : timed runbook
- `resources/osint.md` : responsible OSINT introduction

## Conventions

- No em-dash, no en-dash in produced content.
- Versioned documents are never overwritten: v01 is kept alongside v02.
- All lab material is synthetic and TLP:CLEAR. No real case data.

## Licence

To be decided.
