# portfolio-audit

A free Claude Code skill that audits your portfolio and LinkedIn profile — the way a $300 service would, but better.

Built by [Atif Manzoor](https://atifmanzoor.cloud)

---

## What it does

Runs a full positioning audit in one command. No forms, no spreadsheets, no generic checklist.

It interviews you first — 11 targeted questions across 4 blocks. Then it researches your target market live. Then it reads your portfolio. Then it tells you the truth.

**The output:**
- A diagnosis of what story your portfolio is currently telling vs. what it should
- Live research on what your target market is actually hiring for right now
- Section-by-section portfolio review with specific rewrite suggestions (not just advice — the actual copy)
- A positioning statement written for your exact situation
- A 30-day action plan
- Optional: LinkedIn profile audit
- Optional: Re-audit mode to track progress against a previous report

---

## Requirements

- [Claude Code](https://claude.ai/code) (free tier works)
- Web access enabled (for live industry research and portfolio reading)

---

## Installation

1. Copy the `SKILL.md` file into your Claude Code skills folder:

```
.claude/skills/portfolio-audit/SKILL.md
```

2. Run it:

```
/portfolio-audit
```

That's it.

---

## How it works

**Step 1 — Setup**
Two quick questions: is this a re-audit (do you have a previous report?), and do you want your LinkedIn profile included?

**Step 2 — Interview**
11 questions across 4 blocks: your target role, your background, your current situation, and the gap between what employers see and what you want them to see.

**Step 3 — Live research**
5 WebSearch queries on your specific role and company type. What the market is hiring for right now, not six months ago.

**Step 4 — Portfolio read**
WebFetch reads your portfolio directly. If it can't, you paste the content.

**Step 5 — Report**
A full written audit. Every section is specific to you — no templates, no filler.

---

## Re-audit mode

Run `/portfolio-audit` again after making changes. When asked if you have a previous report, paste the path or contents. The skill will track what improved, what hasn't moved, and what is still the biggest blocker.

---

## LinkedIn audit

Optional. At the end of the interview you'll be asked if you want your LinkedIn profile included. If yes, it adds a dedicated section covering your headline, About section, Featured section, and whether your LinkedIn and portfolio are telling the same story.

---

## Why this exists

Someone offered me a $300 portfolio audit. I said I could build a Claude skill to do it. They called it insulting. This is the skill.

---

## Also by the same author

- [style-extract](https://github.com/atifmanzoorali/style-extract-skill) — Extracts your writing voice through a 15-question interview and produces a Writing Style Profile Claude can use in any session.

---

## License

MIT — free to use, share, and modify.
