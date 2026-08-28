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

### Visa fast-skip (H1B eligibility pre-screen)

Before running a full A–G evaluation on any JD, first scan the posting for a hard visa/eligibility blocker that my H1B status cannot clear. Treat any of these as a fast-skip trigger:

- A **U.S. security clearance** requirement (e.g. "eligible to obtain and maintain a Secret/Top Secret clearance") — these generally require U.S. citizenship.
- An **explicit no-sponsorship** statement (e.g. "we will not sponsor", "not able to consider candidates who require visa sponsorship now or in the future", "must have permanent work authorization").
- An **export-control "U.S. persons only"** clause (ITAR/EAR — citizen, permanent resident, asylee, or refugee only), or "unable to sponsor non-U.S. persons".

**On a trigger:** stop before the full evaluation. Produce a **short report** (header + a one-paragraph work-auth section quoting the blocking clause verbatim + Block G legitimacy tier + Risk Summary), set tracker status **SKIP** with the hard-stop reason in the note, and **hold the PDF**. Do not run Blocks B–F, do not tailor a CV. Note briefly what the role *would* have been worth if I were eligible, so I can see what I'm missing.

**Note:** a generic "must be authorized to work in the US" (with no sponsorship exclusion, clearance, or export-control clause) is **not** a trigger — I am currently authorized on H1B; only the three explicit blockers above fast-skip.

(add more rules above)

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
