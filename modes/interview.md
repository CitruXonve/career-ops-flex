# Mode: interview — Interactive Profile & CV Onboarding

When the user runs `/career-ops interview`, execute this interactive profile/CV interview flow.

The purpose of this mode is to conduct a conversational interview to extract rich context, specific project tasks, technologies used, and measurable business impact to build or enhance `cv.md`, `config/profile.yml`, and `modes/_profile.md`.

---

## Guidelines for the AI Agent

### 1. Load Baseline Context

- Read `cv.md` (if it exists) to understand the candidate's current professional profile.
- Read `config/profile.yml` (if it exists) to check current target roles, location settings, and compensation bounds.
- Read `modes/_profile.md` (if it exists) to examine existing target archetypes and narrative alignments.

### 2. Interview Structure & Tone

- Keep it professional, conversational, and direct. Avoid generic corporate fluff.
- **Rule: Ask exactly ONE question at a time.** Never present a wall of questions; wait for the user's response before asking the next question.
- Always prompt for **specifics**: tools/frameworks used, architecture decisions, and most importantly, **measurable outcomes** (percentages, revenue, performance gains, team size, cost savings).

---

## Step-by-Step Interview Flow

### Step 1: Target Roles & Ambitions

Ask the user about their immediate goals:
- What specific roles are they targeting?
- What are their target salary and total compensation expectations?
- What are their location preferences (remote, hybrid, on-site, geographic limits)?
- Are you a non-citizen and subject to certain limit to take a job (e.g. a new U.S. H-1B petition)? If so, offer a **fast-skip rule** that stops before the full evaluation and files a short SKIP report instead, and ask separately for each trigger whether it should fast-skip (one question at a time):
  - an explicit **no-sponsorship** statement
  - a **U.S. security clearance** requirement
  - an **export-control "U.S. persons only"** clause (ITAR/EAR)
- Update `config/profile.yml` with the target role titles, locations, salary bounds, and work authorization (`location.visa_status`, `location.authorized_in`, `location.needs_sponsorship`).

### Step 2: Experience & Core Achievements

Ask about their most significant professional achievements:
- Focus on the last 2-3 roles.
- For each role, ask: "What was your single most impactful achievement in this position, and what specific projects did you build to make it happen?"
- Extract: What tools/architecture were used?

### Step 3: Digging for Metrics (Business Impact)

Recruiters and ATS scanners look for quantifiable metrics. For the achievements and projects mentioned in Step 2:
- Ask: "What was the measurable outcome of this project? (e.g., % improvement, $ saved, latency reduction, user adoption numbers)"
- If the user doesn't know, help them estimate or frame it qualitatively (e.g., "enabled 12 developers to ship 3x faster").

### Step 4: Uncovering Hidden Skills

Ask about adjacent experience or forgotten skills:
- "What tools, languages, or methodologies do you have experience with that aren't on your main resume?"
- "Any courses, certifications, side projects, or articles you have written recently?"

---

## Step 5 — Apply Updates

Once the interview is complete, or once enough new details have been collected:
1. **Update `cv.md`**: Update the professional summary, rewrite project bullet points to incorporate the new keywords and metrics, and append new skills.
2. **Update `config/profile.yml`**: Update the targets, compensation, and narrative sections.
3. **Update `modes/_profile.md`**: Map the new projects/proof points to the target archetypes and update the adaptive framing rules.
4. **Update `modes/_custom.md`** (only if the user picked at least one fast-skip trigger in Step 1): uncomment the "Work-authorization fast-skip" example block, keep only the trigger bullets they chose, and fill its `{placeholders}` from the user's own words only; delete optional lines they didn't supply. Otherwise leave it commented out.
5. Run `node doctor.mjs` silently to verify project integrity.
6. Provide a summary of the files updated:
   > "✅ Interactive interview completed! Updated your profile:
   > - **CV**: Refined summaries and project bullets with new metrics.
   > - **Profile config**: Updated target roles and comp expectations.
   > - **Custom framing**: Integrated project mappings into _profile.md.
   > - **Work-auth**: Fast-skip on {chosen triggers} / not needed."
