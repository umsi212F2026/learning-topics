# Check six claims from last year's deployment guide

**Used by:** `a-check-2025-guide-claims`, which serves `c-check-vendor-claims`. A study activity:
nothing here can meet the goal.

## Where these come from

In fall 2025, the instructor of this course's predecessor (SI 211) wrote a deployment guide for
students putting a React, Express and SQLite app online. It was careful and accurate when it was
written. Below are six sentences from it, quoted exactly. A year on, some still hold, some have
changed, and one names a free tier that no longer exists. A coding agent trained on pages like this
one may still repeat them.

## The claims

### g1

> **PlanetScale**: MySQL, free tier.

### g2

> **Neon**: Serverless Postgres, free tier, database branching.

### g3

> **Supabase**: Postgres with built-in features, free tier available.

### g4

> I did find one, Render, that seems to provide a free tier with ample resources for both frontend
> and backend hosting.

### g5

> (It also provides a managed Postgres database, but it's only free for the first month, so I had
> you use neon for that instead.)

### g6

> Go to [Neon](https://neon.tech/) and sign up for a free account.

## For each claim, do this

1. Before looking anything up, say which page on the vendor's own site you expect to settle it
   (the pricing page, the docs page on the free plan, the billing docs, a changelog), and why that
   one.
2. Find that page, or the one that actually settles it. Copy the sentence that does, with its
   address and any date on the page.
3. Say whether the claim holds today, has changed (and how), or is gone.
4. Say what the claim leaves out that you would want to know before signing up: whether the thing
   sleeps, what happens past a limit, whether a card is asked for.

Then, looking at all six: which kind of page settled the most claims, and which claims could not be
settled from the vendor's pages at all?

---

## Key, for the tutor

Show the learner everything above this section, not this section. Checked against the vendors'
pages on 2026-10-01. **Vendors change these pages; before using this key, open each address below
and confirm it still says what is quoted. If it doesn't, the page wins and the key is wrong.**

| claim | today | settled by |
| ----- | ----- | ---------- |
| g1 | Gone. PlanetScale's pricing page lists no free plan; the cheapest listed option was a $5/month Postgres single node, and it now sells Postgres as well as MySQL (Vitess). The free Hobby plan ended in 2024. | https://planetscale.com/pricing. The page does not say a free plan existed or ended; it simply has none, which is how a withdrawn free tier usually looks. |
| g2 | Holds. Free plan, "permanent (not a trial); no credit card required": 0.5 GB per project, 100 CU-hours per project, compute scales to zero after 5 minutes idle and that "cannot be turned off". Running out of compute suspends it until the next period; passing storage blocks writes; "None of these limits delete your data." | https://neon.com/pricing (neon.tech now redirects to neon.com) |
| g3 | Holds, with limits the claim leaves out: 500 MB database per project, 2 active projects, and "Free projects are paused after 1 week of inactivity." The pricing page did not say whether a card is required. | https://supabase.com/pricing. The card question is not settled there; the learner should say where else on Supabase's own site they would look, or that they would find out at sign-up. |
| g4 | Holds in part. Static sites are free. A free web service gets 750 instance hours a month per workspace, spins down after 15 minutes without traffic and takes about a minute to come back; past the hours, services are suspended until the month ends. "Ample" is a judgment the page can't settle; the sleep is what the claim leaves out. | https://render.com/docs/free |
| g5 | Changed in kind. Render's free Postgres is free, but it expires 30 days after creation, with a 14-day grace period to upgrade before it is deleted. So it is not "pay after the first month": it is "lose it unless you pay". (Odin's lesson, read in orientation, says the lowest Render databases cost $7, which is a different out-of-date version of the same fact.) | https://render.com/docs/free |
| g6 | Holds, as a statement about signing up: see g2. Included because it carries no detail at all, so the learner has to decide what "free account" would need to mean before it can be checked. | https://neon.com/pricing |

What to draw out at the end: the pricing page settles whether a free tier exists and its headline
limits; the docs page on the free plan settles sleep and what happens past a limit; whether a card
is asked for is often on neither, and Render's own free docs say only that some overages are
"billed ... if payment method exists; otherwise suspended", which is the risk of having a card on
file. Where a vendor's pages don't settle a claim, the honest answer is "I'd find out at sign-up",
not a blog post's word for it. And an absence (g1) is evidence only once you are sure you are on
the page that would list the plan if it existed.
