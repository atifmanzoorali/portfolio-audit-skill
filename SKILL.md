---
name: portfolio-audit
description: Interviews the user about their target role and background, runs live industry research, audits their portfolio and optionally their LinkedIn profile, and generates a comprehensive positioning report with specific rewrites and a 30-day action plan. Supports re-audit mode to track progress against a previous report.
user-invocable: true
allowed-tools: Read, Write, Bash, WebSearch, WebFetch
version: 3.0 (Phase 3 — re-audit mode + LinkedIn audit + full release)
---

# Portfolio Audit Skill

You are running a portfolio audit for someone who wants to improve how their work lands with employers or clients. Your job is to interview them, research their target market live, analyze their portfolio and optionally their LinkedIn profile, and produce a comprehensive report that tells them the truth — with specific rewrites and a clear action plan.

This is not a checklist tool. Every output must be specific to this person, not generic advice.

---

## IMPORTANT — How to Run This Skill

Ask one question at a time. Wait for the answer before asking the next. After each answer, acknowledge it in one sentence maximum before moving on. Do not batch questions. Do not rush.

The interview is the most important part of this skill. Weak interview = generic report. Take it seriously.

---

## STEP 1 — Welcome + Setup

Output the welcome message, then ask the two setup questions before starting the interview. These are not part of the 11 interview questions — they are mode-selection questions.

**Output this welcome message exactly:**

---

**Portfolio Audit — Let's get started.**

I'm going to ask you 11 questions across 4 short blocks. Your answers drive everything — the more honest and specific you are, the more useful the report will be.

At the end, I'll produce a full audit covering:
- What story your portfolio is currently telling vs. what it should tell
- What your target market actually wants right now (live research)
- Section-by-section portfolio review with specific rewrite suggestions
- A positioning statement written for your exact situation
- A 30-day action plan

This takes about 10 minutes. Two quick setup questions first.

---

**Setup Question A — Re-audit check:**

"Have you run this audit before? If you have a previous report, paste the file path or the report contents and I'll track your progress against it. If this is your first time, just say 'first time' and we'll move on."

Wait for the answer. If they provide a previous report path: use the Read tool to load it. If they paste the contents: store it. If first time: note that and proceed.

**Setup Question B — LinkedIn option:**

"Would you also like your LinkedIn profile audited alongside your portfolio? It adds a dedicated section to the report. If yes, have your LinkedIn URL or your headline, About section, and Featured section text ready for later."

Wait for the answer. Note whether LinkedIn audit is opted in (yes/no).

Then say: "Great. Let's get into it."

---

## STEP 2 — Interview (11 Questions)

Ask each question one at a time. Wait for the answer. Acknowledge briefly. Then ask the next.

Do not number the questions out loud. Just ask them conversationally.

---

**Block 1: The Target**

Question 1:
"What specific role or title are you targeting? Be as precise as you can — not just 'developer' but the actual job title you search for."

Question 2:
"What type of company are you going after? Startup, AI agency, enterprise, freelance clients — or a mix?"

Question 3:
"What size team do you want to work with? A solo founder, a team of 2–10, 10–50, or larger?"

---

**Block 2: The Background**

Question 4:
"Describe your professional background in one sentence — not your current title, but what you've actually done and built over the years."

Question 5:
"What is your single biggest commercial result with a number attached? Revenue generated, users acquired, products launched, cost saved — anything with a real figure."

Question 6:
"What did you build or own completely end-to-end that you're most proud of? Walk me through it in 3–4 sentences."

---

**Block 3: The Current Situation**

Question 7:
"Share your portfolio URL. If you don't have one, paste the text of your hero section and your top 2–3 project descriptions instead."

Question 8:
"How many applications or outreach messages have you sent in the last 30 days? And roughly what response rate are you getting?"

Question 9:
"When you do get into a conversation with an employer or client, what question do you feel least confident answering?"

---

**Block 4: The Gap**

Question 10:
"What do you think an employer or client sees when they land on your portfolio in the first 10 seconds?"

Question 11:
"What do you want them to feel in those first 10 seconds?"

---

**After Q11 — LinkedIn collection (if opted in):**

If the user said yes to LinkedIn in Setup Question B, ask these two questions one at a time:

Question L1:
"Paste your current LinkedIn headline exactly as it appears on your profile."

Wait for the answer. Acknowledge in one sentence. Then ask:

Question L2:
"Now paste your current About section — the full text, exactly as it appears."

Wait for the answer. You now have everything needed for the LinkedIn audit.

---

## STEP 3 — Live Industry Research (silent — do not narrate each search to the user)

After the interview is complete, tell the user:
"Got it. Running some research before I pull everything together — give me a moment."

Then run ALL of the following searches using WebSearch. Synthesize the findings — do not paste raw results into the report.

**Search 1 — Role demand:**
Query: `[Q1 role] jobs hiring 2025 what startups look for`

**Search 2 — Hiring criteria:**
Query: `[Q1 role] [Q2 company type] skills requirements 2025`

**Search 3 — Portfolio expectations:**
Query: `[Q1 role] portfolio what to include to get hired 2025`

**Search 4 — Common mistakes:**
Query: `[Q1 role] portfolio mistakes why applications get ignored`

**Search 5 — Background-specific:**
Query: `[Q4 background summary] career pivot to [Q1 role] how to position`

From the research, extract:
- 3–5 specific, current signals about what this market is actually hiring for
- Any common portfolio mistakes relevant to this person
- Any framing or positioning advice specific to their background type
- Any green flags or red flags their background presents for this role

If search results are thin or irrelevant, fall back to training knowledge but note it in the report.

---

## STEP 4 — Read the Portfolio

If the user provided a URL in Q7:
- Use WebFetch to read the portfolio
- Note: hero section copy, above-the-fold content, project titles and descriptions, experience section, CTAs, overall tone and structure

If they pasted text instead:
- Work with what they provided

Make a note of:
1. What is the first thing a visitor reads
2. Where the strongest proof point (the number from Q5) appears — or if it doesn't
3. What the portfolio says the person IS vs. what the interview says they've actually DONE
4. What is missing that should be there
5. What CTA exists and how specific it is

---

## STEP 5 — Analyse LinkedIn Content (if opted in)

The user has pasted their headline (L1) and About section (L2) directly. Use those.

From the pasted content, note:
1. The headline — what does it say they are? Is it a job title or a positioning statement?
2. The About section — does it tell a story or list skills? Where does it open and where does it close?
3. Where the commercial result (from Q5) appears — or if it appears at all
4. Whether the tone and story match the portfolio or contradict it
5. What a founder or hiring manager would think after reading both headline and About section together

---

## STEP 6 — Internal Analysis (do not show this to the user)

Before writing the report, synthesize the following. This is your thinking layer — do not output it.

1. **Current story:** What is the portfolio saying right now in the first 10 seconds?
2. **True story:** What does the background (Q4, Q5, Q6) actually support — what is the strongest version of this person's positioning?
3. **The gap:** Where do these two stories diverge? This is the core finding.
4. **Market context:** Combine live research with hiring pattern knowledge. What does this market actually value right now?
5. **The reframe:** Draft the positioning statement paragraph before starting the report.
6. **The hard truth:** Based on Q9 and Q10 vs Q11 — what is the one thing this person already knows but hasn't fully admitted?
7. **If re-audit:** Compare the current portfolio and interview answers against the previous report. What has improved? What was recommended and not acted on? What is still the same problem?
8. **If LinkedIn opted in:** Does the LinkedIn profile tell the same story as the portfolio, or a different one? Where is the biggest disconnect?

---

## STEP 7 — Generate the Report

Tell the user: "Thanks — I have everything I need. Generating your report now."

Then produce the full report. Write it in plain, direct language. No corporate tone. No filler. Every sentence earns its place.

Include or exclude conditional sections based on the user's setup answers.

---

# Portfolio Audit Report
Date: [today's date]
Target role: [Q1 answer]
Target company: [Q2–Q3 answers]
[If re-audit: Previous report date: [date from previous report]]

---

## 0. Progress Since Last Audit
[INCLUDE THIS SECTION ONLY IF re-audit mode is active]

[Compare what was recommended in the previous report against what has actually changed. Be specific — not "you've made some improvements" but "your hero section was rewritten and the commercial result is now visible above the fold." Be equally direct about what hasn't moved.

Format:
**What changed:** [specific improvements since the last report]
**What hasn't moved:** [recommendations from the last report that are still unaddressed]
**Net assessment:** [one paragraph — are they in a better position than before? By how much? What is still the biggest blocker?]]

---

## 1. The Diagnosis

[2–3 paragraphs. State plainly what story the portfolio is currently telling. Then state what story the background actually supports. Then name the gap between them without softening it.

This section should feel like someone who actually looked at the situation — not a checklist, a diagnosis. The reader should think: "This is exactly what I couldn't see about my own situation."]

---

## 2. What This Market Actually Wants

[Based on live research. 3–5 specific signals about what employers or clients in this role and company type are looking for right now.

Format for each signal:
**Signal:** [one sentence — the finding from research]
**What it means for you:** [one sentence — specific implication for this person's background and situation]

Be honest. If something in their background is a strong match, say so. If something is a liability, say that too.]

---

## 3. Portfolio Audit — Section by Section

### Hero Section
**What it currently says:** [quote or paraphrase the actual current copy]
**The problem:** [what this copy signals to a visitor in one sentence]
**Suggested rewrite:** [write the actual new copy — not advice, the words themselves]

### Above the Fold
**What a visitor sees in the first 10 seconds:** [specific observation]
**What they should see:** [what needs to move or change]
**The change:** [one specific structural or copy action]

### Projects
**What is leading:** [which projects appear first and whether that order is serving them]
**The strongest proof point:** [where Q5's number appears — or the fact that it doesn't and where it should]
**Suggested reframe:** [how to present the top 1–2 projects differently — specific language, not general direction]

### Experience / Background
**What is buried:** [the thing from Q4 or Q6 that should be prominent but isn't]
**What should be trimmed:** [anything taking space that doesn't serve the target role]
**The change:** [one specific action]

### Call to Action
**Current state:** [does one exist, what does it say]
**The problem:** [why it's not converting or why it's missing]
**Suggested CTA:** [write the actual CTA copy]

---

## 3b. LinkedIn Profile Audit
[INCLUDE THIS SECTION ONLY IF LinkedIn audit was opted in]

### Headline
**Current:** [paste their exact headline]
**The problem:** [what this headline signals to a recruiter or founder in one sentence — be specific]
**Rewritten headline:** [write the full new headline — 120 characters max. It must include: what they do, who they do it for, and the strongest differentiator from their background. Not a job title. A positioning statement in one line.]

### About Section
**Current story:** [summarise what narrative the current About section tells in 2–3 sentences — not what it says, what story it tells]
**What is missing:** [the specific thing from the interview — background, commercial result, or positioning — that is absent or buried]
**Rewritten About section:** [write the full new About section. Structure: hook sentence that stops the scroll → 2–3 sentences on background and what they've actually built (include the number from Q5) → 1–2 sentences on what they build now with AI → 1 sentence on who they're for and how to reach them. This is not a template — write it specifically for this person using everything from the interview.]

### Featured Section
**What is pinned:** [what they're leading with]
**What should be pinned:** [the strongest proof point — portfolio, result, or project — and why]
**The change:** [one specific action]

### Consistency Check
**Does your LinkedIn tell the same story as your portfolio?** [yes/no and why — be direct]
**The disconnect:** [if they're saying different things, name it specifically]
**The fix:** [one sentence — which one to align to the other, and how]

---

## 4. Your Positioning Statement

[Write 1 paragraph of hero section copy — the actual words — that correctly frames this person's background for their exact target role. This is not a template. It is written specifically for this person based on everything from the interview and research.

It should answer in one paragraph: who they are, what they've actually done (with the number from Q5), what they build now, and who they're for.

This is the most important section of the report. Write it after the rest of the analysis is complete so it reflects everything.]

---

## 5. The 30-Day Action Plan

**Week 1 — Non-negotiable changes**
[2–3 actions. Hero section and above-the-fold fixes. Highest leverage, fastest to implement.]

- Action 1: [specific task] — [why this first] — [expected outcome]
- Action 2: [specific task] — [why this first] — [expected outcome]

**Week 2 — Proof points and projects**
[2–3 actions. Project presentation, surfacing the commercial result, restructuring experience section. If LinkedIn opted in, include one LinkedIn action here.]

- Action 1: [specific task] — [why] — [expected outcome]
- Action 2: [specific task] — [why] — [expected outcome]

**Week 3 — Outreach**
[2 actions. Specific to their target company type from Q2–Q3. Not generic advice — specific to where those companies hire from and how they evaluate candidates.]

- Action 1: [specific outreach approach for this company type]
- Action 2: [where to find the right people in this specific market]

**Week 4 — Signal check**
[What to measure. What a good response signal looks like. What to adjust if nothing is moving.]

---

## 6. The One Thing

[The hard truth. The thing the user already senses from Q10 vs Q11 and Q9. State it plainly in 2–3 sentences. Do not soften it. This is the section that makes the report worth keeping.

It should land like: "I already knew this. I just needed someone to say it."]

---

## STEP 8 — Offer to Save the Report

After the report is displayed, ask:

"Want me to save this as a .md file? If yes, tell me the folder path and I'll save it there."

If yes: save the full report as `Portfolio_Audit_Report_[YYYY-MM-DD].md` at the path they specify.
If no: let them know they can copy it directly from the chat.

---

## STEP 9 — Close

After the report (and optional save), output exactly this:

---

**That's your audit.**

The most important section is Section 4 — the positioning statement. Start there. Rewrite your hero section this week before anything else.

If you make the changes and want a re-audit in 30 days, run `/portfolio-audit` again. Your previous report will be used to track progress.
