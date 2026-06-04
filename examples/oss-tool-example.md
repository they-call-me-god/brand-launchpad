# Example: Open-Source Tool Brand

Sample run of `brand-launchpad` on a fictional open-source CLI called
**driftwatch** (detects config drift between staging and production).

> All names, numbers, and outputs are illustrative only.

---

## Step 0: Capture

```yaml
project_name: driftwatch
brand_type: oss
real_name_or_alias: "@driftwatch"
one_sentence_what_it_does: "Catches config drift between your staging and production environments before it pages you."
icp:
  who: Platform / DevOps engineers running multi-environment infra
  pain_or_desire: "Works in staging, broke in prod" caused by silent config drift
  where_they_hang_out: GitHub, Hacker News, r/devops, X (infra crowd)
desired_outcome_12mo: 2,000 GitHub stars + 5 recurring contributors
constraints:
  anonymous_required: no
  time_per_week_hours: 5
  camera_comfort: reluctant
  platforms_committed: [GitHub, X, Hacker News]
```

## Step 3: Positioning sentence

> driftwatch is the only drift detector that fails your CI *before* the
> drift reaches production, not after it pages you.

(Counterposition: every incumbent is a *dashboard* you check after an
incident. driftwatch moves the check left into CI — it refuses to be
another screen you forget to open.)

## Step 5: Hero line candidates

| Candidate | Visualize | Falsify | Nobody else |
|-----------|-----------|---------|-------------|
| "Catch config drift in CI, not in the incident channel." | Pass | Pass | Pass |
| "Powerful, lightweight config monitoring for teams." | Fail | Fail | Fail |
| "Your dashboards tell you after. driftwatch tells your CI before." | Pass | Pass | Pass |

Winner: candidate 3. Falsifiable (dashboards are post-incident by design),
visualizable (red CI check vs. a 3am page), and the "before/after" framing
is something no incumbent dashboard can claim.

## Step 6c: Named recurring series

1. **"Drift of the week"** — Friday post dissecting one real-world drift
   pattern (a TLS cert, a feature flag, an env var) and the CI rule that
   would have caught it. Sourced from issues + contributor war stories.
2. **"Shipped this week"** — Wednesday changelog thread in plain English,
   one GIF per merged feature. Turns the commit log into content.
3. **"Reading the source"** — Monthly deep-dive where the maintainer walks
   one module of driftwatch on camera-optional screen share. Recruits
   contributors (the real OSS growth lever, not stars).

## Step 9: Day-21 milestone

Get driftwatch adopted in one real team's CI pipeline (not a toy repo) by
Day 21 — a merged PR in *their* `.github/workflows`, with permission to
screenshot the green check that replaced a would-be incident. Week 4
content is the case study + a "first external CI adoption" release note.

## OSS-specific notes

- **Stars are a vanity metric; contributors are the brand.** The series
  above is weighted toward `Reading the source` and issue-sourced posts on
  purpose — a responsive, legible maintainer converts watchers into PRs,
  and PRs are what keep an OSS brand alive past launch week.
- **The two-handle split for OSS:** main repo + `@driftwatch` is the
  polished feed; the maintainer's personal handle is the B-side lab
  notebook ("why I rewrote the diff engine at 1am"). Keep the project
  account boring and reliable; keep the human account honest.
