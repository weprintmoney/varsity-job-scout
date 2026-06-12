# Varsity Job Scout Agent

**Varsity Women's Club × Tech Maxxing × Protopia AI**
*AI Skills for Breaking into Tech as a Female Athlete Grad*

---

> You've already mastered discipline, resilience, and performing under pressure.
> Now let's apply that same mindset to your career transition — with AI as your ultimate performance enhancer.

---

## What This Is

A reusable AI agent that drops 8–12 warm job opportunities in your inbox every Monday before you wake up — replacing hours of scrolling LinkedIn, Handshake, Indeed, Reddit, Eventbrite, and women-in-tech Discords every week.

**Built for:** Highly educated female athlete grads with real internship/work experience + the leadership, grit, and performance mindset from athletics.

**Targets:** High-growth tech roles (product, growth, data, engineering, operations) and venture capital / investing opportunities where your combination of academics, internships, and proven leadership stands out.

---

## Repo Structure

```
varsity-job-scout/
├── README.md                  # This file
├── SKILL.md                   # The reusable agent playbook (start here)
├── context/
│   └── my_profile.md          # YOUR master resume + preferences (customize this)
├── output/                    # Agent drops weekly results here
│   └── .gitkeep
└── examples/
    └── sample-output.md       # What a good weekly brief looks like
```

---

## Quick Start

### Step 1 — Fill in your profile
Edit `context/my_profile.md` with your actual info. The agent reads this every run. Without it, the agent makes things up.

### Step 2 — Load the skill in Claude
- Open Claude desktop/web → Settings → Capabilities → Skills → Create with Claude
- Or paste `SKILL.md` contents into a Project's instructions

### Step 3 — Trigger it
Say: *"Run my weekly opportunity scout."*

The agent finds, qualifies, ranks, and writes your output files — no extra instructions needed.

---

## The 3 Things You Actually Customize

| Part | File | What to change |
|------|------|----------------|
| Search queries | `SKILL.md` Phase B | Add/remove terms based on your target roles |
| Qualifying bar | `SKILL.md` Phase C | Tighten or loosen YOE, role type, geography |
| Output columns | `SKILL.md` Phase F | Add columns you need to act fast |

Everything else is structural and works for almost any athlete grad profile.

---

## From the Workshop

**Today's goal:** Understand the 8 parts of an AI agent (in sports terms) + build your first reusable skill in under 20 minutes.

This repo is the worked example for Part 2 of the workshop — the Weekly Opportunity Scout.

---

*Made for the squad. Adjust it, share it, make it yours. Your transition is a team sport too.*
