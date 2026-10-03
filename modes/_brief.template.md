# {Your Name} — Triage Brief

<!-- ============================================================
     THIS FILE IS YOURS. Copy it to `modes/_brief.md` (doctor.mjs
     auto-copies it on first run) and fill in the placeholders.
     It is USER LAYER — never auto-updated by `node update-system.mjs`.

     PURPOSE: Compact context for first-pass triage agents
     (`modes/triage.md`). It replaces reading the full evaluation
     stack — cv.md + _shared.md + _profile.md + profile.yml +
     oferta.md (tens of thousands of tokens) — with a single small
     read (~1.5–2K tokens). Full context is still used in full eval.

     KEEP IT SHORT. Every line here is read once per role during a
     batch triage. Include only what changes a go/no-go decision:
     archetypes, comp floor, location policy, hard disqualifiers,
     and your strongest proof points. Leave the deep narrative,
     negotiation scripts, and STAR stories in _profile.md / cv.md.

     PROVENANCE: populate this file only from in-scope files —
     config/profile.yml, modes/_profile.md, modes/_custom.md, cv.md.
     No claim should originate here; every line should trace to one
     of those. Note the date you populated it, and keep it that way
     when editing.
     ============================================================ -->

## Identity
{One line: seniority, discipline, years (employers + dates), location/timezone,
education, work-authorization constraints. e.g. "Senior Backend Engineer — 10+ yrs.
Remote (ET). US citizen, no sponsorship." If you need sponsorship, state the exact
mechanism triage should assume, and any phrasing it must never use.}

## Target Archetypes
The roles you actually want. Triage scores "archetype fit" against this list.
A direct hit scores 4–5; an adjacent title scores 3; a mismatch scores 1–2.
Tag each row *(primary)*, *(secondary)* or *(adjacent — score 3)*.

| # | Archetype | What they buy (your proof) |
|---|-----------|----------------------------|
| 1 | **{Archetype name}** *(primary)* | {the capability/experience that makes you a fit} |
| 2 | **{Archetype name}** *(secondary)* | {...} |
| 3 | **{Archetype name}** *(adjacent — score 3)* | {...; note any sub-flavor that drops it to 3, e.g. "research-heavy → 3"} |

**Analogs that count as direct hits:** {same skills, different titles — e.g.
"Software Engineer, Backend"; "Production Engineer" / "SRE"; "Platform Services"}.

**Weak fit — score 1–2:** {disciplines you don't want — e.g. pure frontend, pure research}.

## Proof Points (use exact metrics in matching)
Your strongest, quantified accomplishments. Triage checks how many map to a JD.
- {Accomplishment — metric, scope, impact}
- {Accomplishment — metric, scope, impact}
- {Accomplishment — metric, scope, impact}
- {Personal/side project — mark it as such so triage never claims production scale}

**Stack:** {languages · frameworks · datastores · cloud · infra · AI/ML tooling}.
**Absent:** {common JD keywords you do NOT have — so triage scores them as gaps,
not as matches}.

## Comp Strategy
| Target | Requirement |
|--------|-------------|
| **{$X–$Y}** | {stated target range — cite `compensation.target_range`} |
| {$Y}+  | {conditions — e.g. higher intensity / on-site acceptable} |

**Hard floor: {$X}** (`compensation.minimum`). Below that, FAIL regardless of other signals.
**Optionally also FAIL on comp:** a published range whose **ceiling** sits below your
target floor — the role cannot reach your range even at the top.

<!-- Optional: note how your target compares to the market median for your
     level/metro, so triage treats your floor as stated, not market-correct. -->

## Location Scoring
How to score the "location" dimension. Adjust to your own policy.
- Fully remote / async-first → **5.0**
- Light hybrid, home metro (flexible, few days/month) → **4.0–5.0**
- Regular hybrid or on-site, **{home metro}** (no move) → **{score}**
- On-site / hybrid, **{metro you've accepted relocating to}** → **{score}**
- On-site / hybrid requiring relocation **elsewhere** → **{score}**
- 5-day mandatory RTO → additional **{deduction}** (if you prefer remote)
- High travel (>25%) → **deduct 0.5–1.0**

## Hard DQ Criteria — instant FAIL (≤ 2.5)
Score ≤ 2.5 immediately and skip detailed analysis if ANY apply. These are the
hard gaps you cannot bridge — be specific so triage can pattern-match them.
Cite where each comes from (e.g. `modes/_profile.md` deal-breakers).
- {e.g. Active license/clearance you do not hold — quote the JD phrasings to match}
- {e.g. Explicit work-authorization exclusion that rules you out — quote the phrasings}
- {e.g. Company stage/size below your minimum}
- {e.g. Primary hands-on skill outside your discipline}
- {e.g. Stated comp ceiling below your floor}
- {e.g. Travel above your limit for the role type}

**NOT a DQ:** {near-misses triage should not fail on — e.g. generic boilerplate
that looks like a DQ phrase but isn't one → score neutral and flag it}.

## Quick Scoring Guide

Bands are relative to `triage_threshold` (`config/profile.yml → pipeline.triage_threshold`,
default **3.5**), matching the verdict table in `modes/triage.md` — so a score at or
above the threshold is PASS, and only the band below it is MARGINAL.

| Score | Verdict | What it means |
|-------|---------|---------------|
| ≥ threshold (default 3.5) | **PASS** | Clears the bar — strong archetype + comp + location, gaps bridgeable |
| 3.0 – (threshold − 0.1) | **MARGINAL** | Borderline — shown to user as one line |
| < 3.0 | **FAIL** | Does not clear the bar — filtered |

## Soft Red Flags (−0.5 each, additive)
Not disqualifiers, but they lower the score.
- {e.g. Level below your target (title/years band that signals junior)}
- {e.g. Posting age > 60 days with no multi-headcount explanation}
- {e.g. Recent company-wide layoffs without the hiring team carved out}
- {e.g. Role mostly outside your discipline (partner-facing / BD vs. engineering)}
- {e.g. Recruiter/agency listing with an unnamed end employer}
- {e.g. A "required" cert you list as a gap}

## Priority Override List — always return PASS regardless of score
Companies you want surfaced no matter what (specific interest, warm intro, etc.).
- {Company name — reason}
