# Skill: Weekly Opportunity Scout

**Trigger:** "Run my weekly opportunity scout" / "Find this week's opportunities" / "Monday scout"

**Purpose:** Find 8–12 warm, qualified job and fellowship opportunities every week — filtered specifically for female athlete grads targeting high-growth tech and VC roles.

---

## PHASE A — LOAD WHAT YOU ALREADY KNOW
*(Always do this first. Never skip.)*

1. Read `output/seen-jobs.csv` — the running log of jobs/events already surfaced or applied to. Never resurface anything on this list.
2. Read `context/my_profile.md` — master resume, internship experience, target roles, academics, leadership from sports, and non-negotiables.
3. If either file is missing — **STOP**. Tell the user to create it first. Never run without context.

**Why:** Without this step, the agent surfaces the same 3 jobs every week or pitches roles requiring 5 YOE.

---

## PHASE B — FIND THE SIGNAL

Search LinkedIn, Handshake, Wellfound (AngelList), VC firm job boards, women-in-tech Discords, and Reddit (r/cscareerquestions, r/womenintechnology, r/venturecapital) using the exact words hiring managers in high-growth tech/VC communities actually use:

**Athlete-explicit language**
- `"former athlete"`
- `"collegiate athlete"` / `"student-athlete"`
- `"Division I"` / `"D1 athlete"`
- `"athletes encouraged to apply"`
- `"competitive background"`

**Culture signals that skew toward athletes**
- `"high-performance culture"`
- `"competitive" + "sales"` OR `"competitive" + "GTM"`
- `"scrappy"` / `"coachable"` / `"hungry"`
- `"build the playbook"`
- `"high-growth" + "operations"`
- `"0 to 1"` / `"founding team"`

**Role types where athlete profiles convert best**
- `SDR` OR `"Sales Development Representative"` + startup
- `"Business Development"` + Series A
- `"Revenue Operations"` / RevOps
- `"Chief of Staff"` + startup
- `"Venture Fellow"` OR `"VC Fellow"`
- `"Recruiting"` + startup
- `"Customer Success"` + SaaS
- `"Growth"` + Series A OR Series B
- `"Product Operations"` + new grad

**Startup-stage signals**
- `"Series A" OR "Series B"` + hiring
- `"fast-paced"` + `"no two days the same"`
- `"generalist"` + startup
- `"new grad"` OR `"analyst program"` + tech

**Why:** Vague "tech jobs" finds noise. These specific phrases surface the high-growth opportunities worth your limited time.

---

## PHASE C — QUALIFY WHAT YOU FOUND
*(This is the whole job. Be ruthless.)*

**Keep if ALL of these are true:**
- High-growth tech or VC role suitable for candidates with strong academics + internship experience (0–2 YOE or new grad / analyst programs)
- Clear path to apply OR warm intro / referral opportunity (community post, event connection, or strong referral culture at the company)
- Signal from the last 14–21 days (or fellowship/event with upcoming deadline)
- Company shows high-growth signals: recent funding, ambitious mission, strong early-career development focus
- Company values or explicitly recruits high-achieving women

**Drop immediately if:**
- Requires 3+ YOE as a hard requirement
- Purely sports/tech crossover roles (unless that's the user's specific goal — check `my_profile.md`)
- No clear apply path or warm intro opportunity
- Already in `seen-jobs.csv`
- Cannot verify from a public source

**Why:** Vague criteria = bad output. Specific bar = only opportunities worth the user's time.

---

## PHASE D — WARM INTRO CHECK

For every opportunity that passes Phase C, check:
- Does the company or any employee appear in the user's `context/my_network.md` (if it exists)?
- Is there a mutual connection visible on LinkedIn?
- Did the opportunity come from a community where the user is already a member?

Flag these with `warm_intro: true` in the output. These get bumped up in ranking.

---

## PHASE E — RANK & CUT

Rank by:
1. Warm intro / referral opportunity available
2. High-growth potential of the role + strong alignment with user's academics, internship experience, and athletic leadership
3. Ease and speed of application + deadline proximity

**Cut to top 8–10.** Quality over volume. If only 5 pass the bar, deliver 5. Never lower the bar to hit a number.

---

## PHASE F — WRITE THE OUTPUT

### File 1: `output/YYYY-MM-DD-opps.csv`
```
Title | Company | Why Fits Athlete | Warm Intro | Link | Deadline | Source | Confidence (H/M/L)
```

- **Why Fits Athlete:** One sentence. Map to a specific athletic skill (e.g., "Captain experience directly maps to the 'player-coach' leadership style they describe").
- **Confidence:** H = verified open posting; M = community mention, likely current; L = inferred from recent activity.

### File 2: `output/YYYY-MM-DD-brief.md`
```markdown
# Weekly Opportunities — Week of [Date]

**This week:** X total screened → Y passed the bar

## Top 5 to Tackle First
[Ranked list with one-line reason for each]

## Full List
[Link to CSV]

## Trends This Week
[1–2 sentences: patterns noticed, e.g., "Heavy VC fellowship recruiting this week — 3 programs with deadlines in 30 days."]

## Warm Intro Flags
[Any opportunities with known connections — action these first]
```

### File 3: Update `output/seen-jobs.csv`
Append every opportunity surfaced this run — whether it made the final cut or not — so it never gets resurfaces.

---

## ATHLETE TRANSLATION RULES

When mapping the user's athletic experience to tech language, always use these translations:

| Athletic Experience | Tech Language |
|--------------------|---------------|
| Captain / team leadership | Cross-functional leadership, player-coach, leading without authority |
| Performance tracking / film review | Data-driven decision making, metrics-oriented |
| Injury recovery / tough losses | Resilience, navigating setbacks, iterating under pressure |
| Recruiting / team culture | Talent identification, culture building |
| Conditioning / practice discipline | Execution discipline, high-output work ethic |
| High-stakes competition | Delivering under pressure, performance in ambiguous environments |

**Non-negotiable:** Never fabricate metrics. Only use numbers from the user's actual experience in `my_profile.md`. If a number would strengthen the output, suggest where the user could add it — don't invent it.

---

## GUARDRAILS

- Never resurface a job in `seen-jobs.csv`
- Never invent company details, funding rounds, or headcount
- Never lower the qualifying bar to hit a volume target
- If the user's profile is missing, stop and ask — don't guess at preferences
- Flag any role that seems like a mismatch even if it technically passes criteria
