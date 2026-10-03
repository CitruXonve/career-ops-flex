# Custom Instructions -- career-ops

<!-- ============================================================
     THIS FILE IS YOURS. It will NEVER be auto-updated.

     Put your own house rules, custom workflows, and automations
     here -- anything you want the agent to ALWAYS do (or never do).

     This is for PROCEDURAL rules ("HOW I want things done").
     For WHO you are (archetypes, narrative, comp, negotiation),
     use modes/_profile.md instead. Keeping the two separate keeps
     each one readable.

     The agent reads this file alongside the system instructions;
     your rules here take precedence over the defaults, as long as
     they don't break the Data Contract (your files are never
     touched, and we never auto-submit an application for you).

     Because this is a user-layer file, anything you write here
     survives `node update-system.mjs`. Put customizations HERE,
     not in CLAUDE.md / modes/_shared.md / other system files --
     those get overwritten on update.
     ============================================================ -->

## House Rules

<!-- Rules the agent should always follow. Examples:
     - Always write evaluation summaries in British English.
     - Never include a photo in my CV (US / ATS-first market).
     - Cap each batch run at 20 listings unless I say otherwise.
     - If a report scores below 6, skip the cover letter. -->

<!-- Worked example -- a work-authorization pre-screen. Uncomment and
     adapt it if you need visa sponsorship; delete it otherwise.

### Work-authorization fast-skip (eligibility pre-screen)

Before running a full A–G evaluation on any JD, first scan the posting for a hard eligibility blocker that my work-authorization situation ({your status / what you need from an employer}) cannot clear. Treat any of these as a fast-skip trigger:

- A **U.S. security clearance** requirement (e.g. "eligible to obtain and maintain a Secret/Top Secret clearance") — these generally require U.S. citizenship.
- An **explicit no-sponsorship** statement (e.g. "we will not sponsor", "not able to consider candidates who require visa sponsorship now or in the future", "must have permanent work authorization").
- An **export-control "U.S. persons only"** clause (ITAR/EAR — citizen, permanent resident, asylee, or refugee only), or "unable to sponsor non-U.S. persons".

**On a trigger:** stop before the full evaluation. Produce a **short report** (header + a one-paragraph work-auth section quoting the blocking clause verbatim + Block G legitimacy tier + Risk Summary), set tracker status **SKIP** with the hard-stop reason in the note, and **hold the PDF**. Do not run Blocks B–F, do not tailor a CV. Note briefly what the role *would* have been worth if I were eligible, so I can see what I'm missing.

Consequences for evaluation:
- A generic "must be authorized to work in the US" with **no** sponsorship language is **not** a trigger — {score it neutral / flag it as an open question}, since many such employers do sponsor.
- {Optional targeting preference, e.g. weight employers with in-house immigration counsel and a filing history above early-stage startups — a preference, not a hard filter.}
- {Optional wording rule, e.g. the exact term generated content must / must never use for your sponsorship need.}

### Work-authorization document requests (recruiters and agencies)

Never advise handing immigration documents to a recruiter, agency, or any intermediary before a written offer. The standing rule: **status category only; documents go to the employer's immigration counsel, post-offer.** This applies to approval notices (including prior employers'), I-94s, passport scans, receipt numbers, and SSN.

When a mode surfaces an intermediary asking for status specifics, point me at {your scripts file, e.g. interview-prep/work-authorization-scripts.md} and log the incident there.
-->

(none yet -- add yours above)

## Custom Workflows

<!-- Multi-step routines you run often, given a short name. Examples:
     - "weekly review": scan my saved portals, evaluate the new roles,
       then give me a one-paragraph summary of the top 3.
     - "prep <company>": pull the JD, generate STAR stories from
       article-digest.md, and draft 5 likely interview questions. -->

(none yet -- add yours above)

## Output Preferences

<!-- How you like results formatted. Examples:
     - Reports: lead with the score and the one-line verdict.
     - Show the per-step token breakdown after a batch run.
     - Save PDFs date-first: YYYY-MM-DD-company.pdf -->

(none yet -- add yours above)

## Off-Limits

<!-- Things the agent must never do for you. Examples:
     - Never auto-fill or submit an application without showing me first.
     - Never edit a system file to customize my setup -- put it here. -->

(none yet -- add yours above)
