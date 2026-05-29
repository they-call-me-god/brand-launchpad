---
name: brand-launchpad
description: >
  Personal or project brand launch playbook distilled from 4 source videos
  (Caleb Ralston brand course, Oren John creative living-portfolio, Harry Dry
  copywriting, 100k content 2026). Takes a project or person and outputs:
  brand DNA, positioning, content cadence, 3 native formats, 30-day plan,
  and a copy-tested hero line. Use when the user says "build a brand for X",
  "personal brand", "make X a brand", "brand strategy", "content strategy",
  "launch plan for X", "what should I post about X", or names a specific
  project and asks for promotion / awareness / followers / clients.
---

# brand-launchpad

Reusable launch playbook. Project-agnostic. One run produces a complete brand
plan for any project (digital product shop, agency service, personal handle,
SaaS, info product) saved to `Projects/<name>/brand/`.

## When to invoke

- User asks to build/launch/strategize a brand for any project or themselves
- User finishes building a product and asks how to get attention
- User asks "what should I post" or "how do I grow [X]"
- User mentions one of the 4 source thinkers (Caleb Ralston, Oren John, Harry Dry)
- User says "brand kit", "content cadence", "positioning", "hero line"

Do NOT invoke for: ad-account audits, ad copy generation, or one-off post drafting.

## How to invoke (universal call patterns)

This skill is project-agnostic. It works for any of:

- **Personal brand**: the user themselves, no specific project
- **Studio brand**: anonymous or aliased handle that aggregates multiple
  projects
- **Product brand**: one shipping product, SaaS, app, or info product
- **Service brand**: agency, freelance offer, consulting practice
- **Open-source / repo brand**: a library or framework with a maintainer
- **Newsletter / podcast brand**: pure content asset, no product yet

Invocation shapes the user can use:

```
build a brand for <project name>
launch <project name> publicly
make <project> a brand
brand kit for <person or studio name>
personal brand for me
positioning strategy for <project>
30-day content plan for <project>
```

Default project resolution order:
1. If the user names a project that has `Projects/<name>/`, use that.
2. If the user names themselves or "me", treat as personal brand and
   write outputs to `Projects/personal-brand/` (create if missing).
3. If the user names a brand-new project, create `Projects/<name>/` and
   the `brand/` subfolder.
4. If ambiguous, ask one clarifying question, then proceed.

## Brand-type variants

Choose the right variant before Step 1. Each variant changes a few
defaults but the 11 steps are identical.

| Variant | Handle default | Cadence floor | Format weighting | Notes |
|---------|----------------|---------------|------------------|-------|
| Personal (Living Portfolio) | user's real name | 1 post/month, 1 email/quarter | Format C (showcase) heavy | Oren's default path |
| Personal (Full Creator) | user's real name | 3 posts/week min, daily ideal | Even 4:2:1 across A/B/C | Brier's full-time path |
| Studio (anonymous) | `@studioname` | 3 posts/week min | Format A + B, no Format C (faceless) | Oren's anonymous studio path |
| Product | `@productname` | Daily on launch month, 3/wk after | Format A (BTS) heavy on launch | Push BOF to 2/wk in launch month |
| Service | user's real name + service phrase | 3 posts/week | Format B (carousel) heavy | LinkedIn primary, not Instagram |
| Open-source | `@reponame` or maintainer name | 2 posts/week | Format B + B (mostly carousels) | GitHub README is part of brand kit |
| Newsletter / podcast | newsletter or show name | 1 episode/wk + 3 promo posts | Format C clip-heavy | Each episode generates 5 to 7 posts |

When in doubt, default to **Studio** for projects and **Personal
(Living Portfolio)** for individuals.

## Sources baked in

| Source | Core idea pulled |
|---|---|
| Caleb Ralston brand course (6h) | Brand = intentional pairing done consistently; 4-question brand journey; positioning by gap; 3-part story (catalyst / core truth / why audience cares); educational content scales trust |
| Oren John living-portfolio (29 min) | Living Portfolio over Behance; Audience of 10; 3 formats only (BTS, carousel, showcase); 3 routes (named / studio / creator); 1 post/month + 1 email/quarter floor |
| Harry Dry copywriting (76 min) | 3-rule test (visualize / falsify / nobody else); facts > adjectives; conflict every sentence; point A to point B; 20+ rewrites; Kaplan's law |
| 100k content 2026 (Brier Cochran) | Personal brand is the #1 asset; 1% better daily; counterposition; ideation faucets (Reddit, secondary TikTok, internal data, 5+5 competitors); untangle data (hook/format/topic/illustration); 4:2:1 weekly mix (top of funnel / mid / bottom) |
| Internal rework (signal-over-cadence) | Signal accumulation > output cadence; source-artifact pipeline (1-2 real events to 5-6 derivatives); 5 named recurring series for audience memory; visual variety rule (4+ surfaces/week); positioning by thinking, not demographic; two-handle studio pattern; proof-first month-1 milestone for service brands |

## Inputs needed

Ask the user only what you cannot derive from the project's existing notes
(`Projects/<name>/overview.md`, `architecture.md`). Specifically pull:

- What the project does in one sentence
- Who buys / hires / follows (current ideal customer)
- What outcome the user wants (sales, hires, followers, authority, calls booked)
- Whether the brand is under user's real name or a studio handle
- Platforms the user is willing to post on (default: Instagram + LinkedIn)
- Constraints (anonymous? time per week? camera-shy?)

If notes exist, read them first and only ask for the gaps.

## Process

### Step 1. Brand Journey (Caleb's 4 reverse-engineered questions)

Reverse-engineer from desired outcome to today's action:

1. **Desired outcome.** What does winning look like in 12 months? Be specific:
   "30 paid Gumroad customers/month" beats "make money".
2. **Be known for.** What does the audience have to inherently associate with
   the brand for outcome #1 to happen?
3. **Do.** What actions, repeated, create that association?
4. **Learn.** What does the user need to learn this week to start doing #3?

Save answers to `brand-journey.md`.

### Step 2. Associations (positive AND negative)

Two lists:
- **Pair with**: 3 to 5 concrete things the brand wants to be inherently
  associated with. Concrete, not adjectives. "Working voice agents for SMBs"
  beats "AI expertise".
- **Do NOT pair with**: 3 to 5 things to avoid. Includes specific people,
  niches, and aesthetics. This is Caleb's "stand out by what you refuse to
  associate with" rule. Be willing to name names privately in this file.

Save to `associations.md`.

### Step 3. Positioning gap (Caleb + Brier counterposition)

Find the gap. Two questions:
1. What is everyone in this niche saying that the user disagrees with?
2. What story / lens / personality / experience does the user have that no
   competitor has?

Output a single positioning sentence in this shape:
`<Project> is the only <category> for <ICP> that <unique mechanism / belief>.`

Then output the **counterposition list**: 5 to 7 niche competitors and the
specific gap the project occupies vs each. This is Brier's "give away the
sauce, then counterposition" move.

**Position by thinking, not by demographic**. A demographic spine (age,
region, profession-as-identity) is the weakest form of positioning because:
- It is imitable in months as more people in that demographic enter
- It frames the brand around *who the operator is* instead of *how they
  think*, which limits the work the brand can carry as the operator
  matures
- It pulls the audience toward a parasocial relationship with the
  person, not toward the systems / products / craft

The strongest positioning legs are *taste*, *operational thinking*,
*specific deep knowledge*, *adversarial belief vs the dominant frame*.
A demographic fact (age, country, role) is a one-time bio mention, not
a positioning leg. If the first draft positioning sentence leans on
who-the-operator-is, rewrite until it leans on how-they-think.

Save to `positioning.md`.

### Step 4. Brand kit (Oren)

Decide and lock:
- 2 to 3 color combos
- 1 to 2 font pairs
- A small set of icons or illustrations
- A typographic / visual tic that becomes recognizable before the caption is
  read (Oren's "trademark visual tic" rule)

Save to `brand-kit.md`.

### Step 4b. Handle reality check + handle architecture

Before locking the brand-kit and before any external surface uses the
handle, check actual availability on every platform the user will be on
within 12 months (IG, YouTube, TikTok, X, Threads, GitHub org, Beehiiv).
Clean single-word handles are almost always taken. Pre-decide the
fallback pattern so the brand kit stamps the right handle from day 1:

- Triple-letter: `@brandnameee`
- Suffix: `@brandname.labs`, `@brandname.studio`, `@brandname.hq`
- Underscore: `@brand_name` (last resort, weakest)

Then decide the **handle architecture**: many studio brands benefit
from a two-handle pattern, not one:

| Handle | Role |
|--------|------|
| Main `@brandname` | Polished face. Format A / B / C only. Brand-kit applied. Source-artifact derivatives. Status bar visible. |
| B-side `@brandname.notes` | Public lab notebook. Raw stills, tracebacks, cost screenshots, whiteboard photos. No brand-kit overhead. Daily 1-3 posts. "Never empty" account. |

The B-side is where Caleb's vulnerability rule lives as a recurring
venue, so it does not dilute the main feed. Cross-account protocol:
main account references B-side posts on Friday teardowns and Series 4
cost posts (1-direction discovery flow), B-side never references main.

Save the handle architecture to `handles.md`. Make `handles.md` the
single source of truth and stop scattering handle references across
positioning / hero-line / brand-kit.

When the brand is a **service** with a real product, the two-handle
pattern is recommended. When the brand is a **personal living portfolio**
or **newsletter**, the single-handle pattern is fine, do not invent a
second account just because the skill suggests it.

### Step 5. Hero line (Harry Dry's 3-rule test)

Write the brand's single hero line that goes on the bio, landing page, and
pinned post. Apply Harry's three tests:

- **Visualize**: can the reader close their eyes and see it?
- **Falsify**: is it true or false (not opinion-shaped air)?
- **Nobody else**: could a competitor copy-paste this and have it still be
  true? If yes, kill it.

Iterate until all three pass. Show the user 3 candidate hero lines in a
table with a Pass/Fail mark per test. Use facts not adjectives ("8/10 booking
calls answered in under 4 seconds" beats "lightning fast"). Apply Kaplan's
law: cut every word not doing work. Target 12 words or fewer.

Save to `hero-line.md`. Include the 20+ rewrite trail so the user can see
why the final won.

### Step 6. Three native formats (Oren)

Lock three formats only. The user posts in one of these three molds every
time. No new format invention allowed.

1. **BTS / transformation** (6 to 15 sec iPhone clips of work in progress
   into the polished result)
2. **Creative carousel** (4 to 8 slides applying the brand kit to work or
   life lessons)
3. **Straight showcase** (user on camera with the product, in a styled
   environment)

Save to `formats.md` with 2 example post outlines per format using the
specific project.

### Step 6b. Source-artifact pipeline

**Critical**: do not let the 30-day plan rely on inventing 7 unique
topics per week. That model burns the operator out and produces
isolated posts with no narrative compounding. Replace it with the
source-artifact pipeline.

A **source artifact** is a real operational event the project produces:
- A cron failure with stack trace + fix commit
- A real customer call (with permission) with the call log
- A measurable workflow before/after at a real client
- A cost spike + the optimization that fixed it
- A new architectural decision recorded with logs proving the call

For each source artifact, generate the standard derivative set across
1 to 2 weeks:

| Derivative | Where | Format |
|------------|-------|--------|
| Reel showing the artifact happening | Main IG + cross to YT Shorts | A1 or A2 |
| Carousel explaining the architecture | Main IG + LinkedIn doc | B1 / B2 / B3 |
| LinkedIn text or document post | LinkedIn | B (as PDF) |
| Raw screenshot on B-side handle | `@brand.notes` IG | A still |
| Newsletter postmortem (quarterly bundle) | Beehiiv | letter |
| Future YouTube teardown (monthly) | YouTube long-form | C1 |

Target: **1 to 2 source artifacts per week, 5 to 6 derivatives each**.
This produces 5 to 12 posts/week from 1-2 real events, not 7 invented
topics. Daily Reels become re-cuts and angles on the week's artifacts:
same event, different camera, different overlay, different beat.

Add the source-artifact pipeline section to `formats.md`.

### Step 6c. Recurring named series

Without recurring named series, posts read as isolated units. With
them, audience memory compounds and the brand owns categories of
thought in the feed.

Define 4 to 6 named series. Each must have:
- **A name** (3-5 words, distinctive enough to stencil on slide 1)
- **A slot** (which day of the week, which format)
- **A cadence** (weekly, biweekly, every 3 weeks, monthly)
- **An absolute rule about what counts** (real failure only / real
  cost only / real before-after only, no fabricated content)
- **A required-pieces checklist** (must include the stack trace, the
  cost number, the fix commit, the before/after diagram, etc.)

Default series library for an operator-shaped brand:
1. **"Why this [thing] failed"** — Friday slot, replaces or pairs
   with the weekly ledger. Real failure only.
2. **"Replacing operational friction"** — monthly long-form
   + Wednesday setup carousel. Real business workflow.
3. **"Humans still needed here"** — every-3-weeks Monday contrarian.
   Workflows where automation fails.
4. **"Cost to run this [system]"** — every-2-weeks Wednesday tactical.
   Real line-item costs.
5. **"[Adversarial belief] > [dominant frame]"** — every-2-weeks
   Monday contrarian (rotates with series 3). Specific architecture
   call with numbers.

For non-operator brands (personal living portfolios, info products,
SaaS), invent the equivalent: name the 4-6 categories the brand will
own, set slots and cadences, write the rules.

Critical: every post in a series must visibly carry the series banner
in the first 2 seconds of the Reel or on slide 1 of the carousel.
Without the banner, the post reads as one-off content again and the
series compounding is lost.

Save to `recurring-series.md`.

### Step 6d. Visual variety menu

A common failure mode is the operator over-indexing on one visual
surface (terminal scrolls, talking head, screen recordings). The lane
saturates and engagement collapses fast. The skill must explicitly
demand a variety floor.

**Rule**: at least 4 different visual surfaces in any given week's 7
Reels. If 5 of 7 are the same surface (e.g. terminal), kill 2 and
replace with a different surface.

Default visual variety menu for an operator-shaped brand:
- Whiteboard breakdowns (camera on the whiteboard, no face needed)
- Business process maps drawn live (Mermaid + screen rec)
- Annotated screenshots of real logs (boxes + arrows in red)
- Before/after architecture diagrams
- Cost breakdown overlays (line-item tables as the whole frame)
- Real call clips (with explicit permission)
- Location reality shots (the actual client site)
- Receipt shots (payment screenshots, customer DMs, calendar bookings)
- One brief talking head per post for context, never as the whole post

For non-operator brands: build the equivalent menu specific to the
project (product photos, customer reactions, behind-the-scenes of the
craft, finished work, raw materials, etc.). The rule is variety floor,
not the specific menu.

Add the visual variety menu and the 4-surfaces-per-week rule to
`formats.md`.

### Step 7. Weekly content mix (Brier's 4:2:1, but driven by source artifacts)

Out of 7 posts/week (or whatever the user commits to), split:
- **4 top-of-funnel** posts (high TAM, still on through-line, designed for
  reach: contrarian opinion / hot take / industry shift / "5 X for Y")
- **2 middle-of-funnel** posts (blow their mind: tactical breakdown,
  "here's how I do X step by step")
- **1 bottom-of-funnel** post (sneak peek inside: "what working with me
  looks like / what a customer gets")

Plus daily stories (intimate, nurturing, no discovery pressure).

**Optimize for signal accumulation, not output cadence**. The driver is
1 to 2 real source artifacts per week, not 7 invented topics. Every Reel
and carousel is a derivative of one of those artifacts (see Step 6b).
The 4:2:1 funnel split is *applied to the derivatives* of the week's
artifacts, not used to demand 7 separate content topics from thin air.

Lock the recurring-series rotation into the funnel split (TOF slot
gets Series 3 or 5 rotating, MOF gets Series 2 or 4 rotating, BOF gets
Series 1 every week, adapt to the project's specific series).

Save to `content-mix.md`. Include 2 specific post ideas per slot for week 1.

### Step 8. Ideation faucets (Brier)

Set up four permanent idea sources so the user never runs dry:
1. **Reddit faucet** — list 3 subreddits relevant to the niche, instruct
   user to paste top-of-month thread into ChatGPT once a week
2. **Secondary TikTok** — new account following only the niche, save outlier
   videos (outlier = >3x that creator's baseline, not just absolute views)
3. **Internal data** — every Sunday, find the week's top post and reduce
   it to a single buzzword; next week make another video on that buzzword
4. **5 + 5 competitors** — 5 inside the niche (steal topics) and 5 outside
   (steal formats). Mash them.

Save to `ideation-faucets.md` populated with the actual subreddit names,
TikTok handles, and competitors for this user's niche.

### Step 9. 30-day day-by-day execution plan

Generate a calendar from today's date forward, 30 rows. Each row has:
- Date
- Format (BTS / carousel / showcase)
- Funnel slot (TOF / MOF / BOF)
- Series tag (which of the 4-6 named series from Step 6c, or "none")
- Working title
- Hook (Harry Dry tested)
- One-line CTA

Day 1 to 7 are fully written. Day 8 to 30 are slot-filled with placeholders
the user fills weekly using the ideation faucets. Restructure each week
around the **1 to 2 source artifacts** the user will produce that week
(see Step 6b), not around 7 invented topics.

**Proof-first month-1 milestone for service/product brands**. For any
brand that sells a real product or service to a real customer (not just
personal-brand-as-content), the most important mover in the first 30
days is **getting one real customer deployment within Day 21**, free or
token-paid, so that all content from Week 4 onward uses real-customer
data instead of self-tested demos. Proof density is the bottleneck on
conversion, not posting frequency.

Add a "month-1 milestone" section to the top of `30-day-plan.md` with:
- The specific deployment target (one clinic, one client, one paid
  user, one pilot)
- Week 1-2 cold outreach sub-tasks
- Week 3 deployment + first real-data capture sub-tasks
- Week 4 content all sourced from the real deployment

For non-service brands (personal living portfolios, OSS, newsletters),
swap the milestone for the equivalent proof-event: "first paying
subscriber", "first cited by a known name", "first repo with 100
stars", "first interview / speaking invitation".

Save to `30-day-plan.md`. Use absolute dates, not "day 1 / day 2".

### Step 10. Energy + environment rules (Caleb)

Write the user's specific:
- **Energy rhythm**: which hours of the day are peak; protect that block
  for filming like a meeting
- **Film-day environment rules**: who reviews drafts, who hits the "this is
  good" signal, how feedback is given (Caleb's nod / fist-bump / specific
  praise protocol). For solo creators: write a personal-checklist version
  ("after each take: rewatch, mark one line that was great, mark one to cut")
- **Standards bar**: 9/10+ ships (Harry's standard). Anything else gets
  cut or reshot.

Save to `operating-rules.md`.

### Step 11. Update todos and link

- Append daily-posting block to `Notes/todos.md`
- Add a one-line entry to your master index linking the new
  `Projects/<name>/brand/` folder
- If the project's `Projects/<name>/session-log.md` exists, append today's
  session entry

## Outputs (all saved to `Projects/<name>/brand/`)

```
Projects/<name>/brand/
├── brand-journey.md
├── associations.md
├── positioning.md
├── brand-kit.md
├── handles.md
├── hero-line.md
├── formats.md
├── recurring-series.md
├── content-mix.md
├── ideation-faucets.md
├── 30-day-plan.md
└── operating-rules.md
```

## Guardrails

- No em dashes anywhere in outputs.
- Use facts not adjectives. "300 prompts shipped in 30 days" beats "prolific".
- Every claim falsifiable. Strip "amazing", "revolutionary", "best", etc.
- Hero line max 12 words. Bio max 220 chars per platform.
- No "build in public" advice as the headline tactic (Brier's hard stance,
  inherited here). Building in public is fine as flavor, not strategy.
- If the project is anonymous-by-design, route the user to the **Studio**
  variant (Oren's "anonymous studio launch" path). Do not insist on real
  name.
- Default platforms: Instagram + LinkedIn. Add TikTok only if user is OK
  with starting under a separate handle to bypass IRL-friend insecurity
  (Brier's tip).
- One post per month + one email per quarter is the **floor**. If the user
  cannot commit to 3 posts per week, lock the floor and stop. Do not let
  them oscillate (Oren's hard rule).

## Anti-patterns to refuse

- "Just go viral once." Brand is built on stacked posts, not one hit
  (Brier's ghost-follower warning).
- "Use AI to write the scripts." AI for ideation only, never for the script
  itself (Harry Dry: taste + conviction + experience are non-replaceable).
- "Optimize for follower count." Reframe to follower quality (Brier's
  Michigan Stadium vs 10-CEO-room exercise).
- "Build a separate brand for every product the user makes." Counter: one
  living portfolio with the user as the through-line. Sub-products live
  under it.
- **"Post 7 unique topics a week."** This is the cadence-over-signal trap.
  Counter: 1 to 2 source artifacts per week feed 5 to 12 derivative posts.
  Same event, different angle.
- **"Lead with the demographic gimmick."** Age + region + role as the
  headline positioning is the weakest leg. Counter: position by thinking
  (taste, operational lens, deep knowledge, adversarial belief).
  Demographic is a one-time bio mention.
- **"Wait for inbound from posts."** For service/product brands, posting
  without one real customer deployment in month 1 produces demo-content
  forever. Counter: the Day-21 real-deployment milestone runs in parallel
  with the posting plan, not after it.
- **"Only post terminal scrolls / talking heads / one visual surface."**
  Counter: 4-surfaces-per-week minimum from the visual variety menu.
- **"Skip the recurring series; just post good content."** Without named
  recurring series, posts read as isolated units with no compounding.
  Counter: 4-6 named series with banners visible in first 2 seconds.

## Universal capture template (Step 0)

Before Step 1, fill this once per project. Saves time on all later steps.

```yaml
project_name: <kebab-case>
brand_type: personal | studio | product | service | oss | newsletter
real_name_or_alias: <handle>
one_sentence_what_it_does: <fill>
icp:
  who: <buyer / hirer / follower>
  pain_or_desire: <what they want changed>
  where_they_hang_out: <platforms, communities>
desired_outcome_12mo: <one specific number + one qualitative win>
constraints:
  anonymous_required: yes | no
  time_per_week_hours: <int>
  camera_comfort: yes | no | reluctant
  platforms_committed: <list, default IG + LinkedIn>
existing_assets:
  website: <url or none>
  audience: <existing handles + follower counts>
  visual_identity: <link to existing brand-profile.json if any>
```

## Application examples (seed library, expand over time)

Drop a row here every time the skill is used on a new project, so
future runs have priors to lean on.

| Project type | Brand type | ICP | Through-line | Positioning gap |
|---------|-----------|-----|--------------|-----------------|
| Digital product shop | Studio | Creators / solopreneurs buying $7 to $17 templates | "A script runs the shop" | Show actual code + weekly ledger vs guru screenshots |
| Faceless content studio | Studio | Niche aesthetic audience | Visual style + automation | Faceless studio with literally autonomous output |
| B2B outreach pipeline | Service | AI builders / agencies | "I sent 1000 cold emails with a pipeline" | Operator voice vs agency-bro voice |
| Voice agent for SMBs | Service | Indian clinic / salon owners | "Voice agent that picks up before the third ring" | Local-language coverage, local pricing, real demos |
| Self-iterating portfolio | Personal (Living Portfolio) | Recruiters + collaborators | "The site rewrites its own copy daily" | The artifact is the proof |
| GitHub profile | Personal (Living Portfolio) | Other devs | Animated, self-updating profile | README is the resume |

To add a new row: at the end of any successful run of this skill, ask
the user "should I add this project to the seed library?" and append.

## Iteration cadence

After 30 days, return to the user with this 7-question retro:
1. Which posts hit the user's "viral for you" baseline (3-5x normal)?
2. What single buzzword summarizes those? (Brier's untangling-data rule)
3. Which of the three formats outperformed?
4. Which content mix slot underperformed and should be cut?
5. What did the audience ask about in DMs / comments? (Caleb's social
   listening rule)
6. **Which named recurring series outperformed?** Kill the bottom 1,
   double down on the top 1, leave the middle alone.
7. **Did the month-1 proof milestone land?** If yes, Week 5 onward
   content is 100% real-deployment-derived. If no, diagnose: was
   outreach the bottleneck, the offer, or the close? Fix that before
   producing more demo content.

Use the answers to rewrite the next 30-day plan. Do not start from scratch.

#skill #personal-brand #content-strategy
