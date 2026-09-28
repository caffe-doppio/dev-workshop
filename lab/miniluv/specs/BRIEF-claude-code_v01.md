# BRIEF: Miniluv Citizen Services, specs and alpha landing page

| Field | Value |
|-------|-------|
| Date | 2026-09-28 |
| Version | v01 |
| Author | Sasha (Et deux mains) |
| Executor | Claude Code, in an isolated session |
| Deadline | Sunday 2026-10-04 (workshop on Wednesday 2026-10-07) |
| Repository root | `/Users/apple/projet_DFF/hub/workshop/` |
| Working folder | `lab/miniluv/` |

This brief is self-contained. Read it fully, then read `README.md` and `support/support_EN_v01.md` at the repository root before any file operation.

---

## 1. Context

"Borrowed from the Lab" is a 60 minute workshop for the Digital Freedom Fund InterHub (Amsterdam, 2026-10-07). Audience: mixed. AI Hub participants are technical; Digital Democracy Hub participants are lawyers who may never have opened a browser console.

The lab needs a **fictional public service** that participants document as evidence: open DevTools, find the calls that contradict the screen, export a HAR, fingerprint it (SHA-256), anchor it (OpenTimestamps), encrypt it (age) and hand it to another group.

The service reproduces **patterns** observed in real French public portals, **never their data, branding or code**.

## 2. Creative direction

- Pure Orwellian dystopia. Working name: **Miniluv Citizen Services** (Ministry of Love). Name to be confirmed by Sasha.
- Original slogans only. **Do not quote the novel.** Examples: "WAITING IS SERVICE", "YOUR FILE KNOWS BEST", "ACCESS IS A PRIVILEGE".
- Tone: cold, bureaucratic, slightly absurd. Humour must survive a room of lawyers: dry, not slapstick.
- Visual identity invented from scratch. Forbidden: Marianne, tricolour, DSFR, `gouv` wording, any resemblance to a real government site.

## 3. Pedagogical scenarios the service must support

| ID | Pattern | What the screen says | What the wire says | What participants must find |
|----|---------|----------------------|--------------------|------------------------------|
| S1 | Front overrides back | "Access denied: your file is under review" | Eligibility endpoint returns an explicit "allowed" value | The contradiction between UI and API answer |
| S2 | Hidden inventory | "No appointment available" | Slots endpoint returns available slots | The data the UI chooses not to show |
| S3 | Hidden bug | Nothing | A response carries a field that should never reach the browser (working idea: `citizen_loyalty_score`) | That the portal leaks, then decide what to do |

- S1 and S2 must be findable by a beginner in under 10 minutes with DevTools Network tab only.
- S3 must be findable but not obvious: it rewards reading full responses.
- Console logs are deliberately talkative and on theme (for example `[MINILUV] Citizen observed.`). They guide beginners without giving S3 away.

## 4. Hard constraints

- **Static only.** Plain HTML, CSS, vanilla JavaScript. No framework, no build step, no backend, no database.
- "API" endpoints are static JSON files served under an `/api/...` path, fetched by the page.
- Runs identically on a VPS and **offline** with `python3 -m http.server` from the site folder. This is the fallback if the venue Wi-Fi fails.
- **No third-party requests.** No CDN, no Google Fonts, no analytics. System font stack or self-hosted fonts.
- **Only synthetic data.** Fictional citizens, fictional identifiers. Nothing resembling a real person, a real identifier format or a real administration.
- The "bug" exposes fake data only. No real vulnerability anywhere: no user input reaching a server, no upload, no eval.
- Permanent visible banner: "FICTIONAL TRAINING ENVIRONMENT".
- `robots.txt` disallowing all, `<meta name="robots" content="noindex, nofollow">` on every page.
- `/.well-known/security.txt` present and valid (RFC 9116), contact to be provided by Sasha.
- Strict Content Security Policy compatible with the above (via meta tag in alpha, header later on the VPS).
- Accessible: semantic HTML, keyboard navigation, readable contrast on a projector.
- English only.

## 5. Deliverables

### D1. Spec: `lab/miniluv/specs/SPEC-miniluv_v01.md`

- Personas: 3 to 5 fictional citizens, each mapped to scenarios (who triggers S1, S2, S3).
- Pages and user flow (landing, fictional login by choosing a persona, citizen dashboard, appointment page).
- Endpoint list with full JSON examples, one per persona where relevant.
- Console log catalogue.
- For each scenario: expected participant path, the exact response fields that constitute the evidence, and a one-sentence "what counsel should say".
- Fixture plan: which HAR captures and `.ots` anchors must be pre-produced for the offline fallback and the verification demo (anchors need several hours to confirm, so they are produced days before).
- Open questions list (section 7 below, plus any new ones).

### D2. Alpha landing page: `lab/miniluv/site/`

- `index.html`, one CSS file, one JS file.
- Landing page with identity, slogans, banner, persona selection leading to a placeholder dashboard.
- At least S1 wired end to end with one persona, so the full capture exercise can be rehearsed.
- A short `lab/miniluv/README.md` explaining how to run it locally.

**Out of scope for this session:** the forged piece used in phase 7 and the answer key. They belong to the facilitator and live in `facilitation/private/`, which is gitignored. Do not create or describe them.

## 6. Working rules

- Before creating any file or folder: check existence. Never overwrite without asking. Never delete structural files (README, TODO, CHANGELOG).
- After creating files: update the "Arborescence" section of the root `README.md`.
- Versioned documents are never overwritten: a new version is a new file (`_v02`), the previous one stays.
- Errors found in already written content are logged as corrections (`C-001`, ...), not silently fixed.
- No em-dash, no en-dash anywhere, including code comments and UI text.
- Mark any uncertain technical claim in the spec as `[Hypothèse]` inside a `> [!NOTE]` block. No other epistemic tags in this public repository.
- Git: **do not commit.** At the end, output separately (1) the `git add` commands with explicit paths, never `-A` or `.`, and (2) a commit message in English, prefixed with a gitmoji shortcode (https://gitmoji.dev/), for example `:sparkles: Add persona selection to landing page`. Nothing else around them.

## 7. Open questions to ask Sasha before writing

1. Final name and at least one slogan approved?
2. Hosting target and domain (planned: subdomain of etdeuxmains.fr on a VPS)? Needed for `security.txt` and CSP.
3. Should the service set a fake session cookie, to make the HAR look realistic and to teach "a HAR contains your session"?
4. Number of groups expected, to size personas and fixtures?
5. Is the facilitator demo (phase 4, 3 minutes on the big screen) done on a dedicated persona that participants will not use?

Ask these first, in one message, then proceed.
