# Key: check-2025-guide-claims

**For the tutor only.** Used by `a-check-2025-guide-claims`. Never show this file to the learner; the learner's copy is `check-2025-guide-claims.md`.

Show the learner the whole of the task file and none of this one. Checked against the vendors'
pages on 2026-10-01. **Vendors change these pages; before using this key, open each address below
and confirm it still says what is quoted. If it doesn't, the page wins and the key is wrong.**

| claim | today | settled by |
| ----- | ----- | ---------- |
| g1 | Gone. PlanetScale's pricing page lists no free plan; the cheapest listed option was a $5/month Postgres single node, and it now sells Postgres as well as MySQL (Vitess). The free Hobby plan ended in 2024. | https://planetscale.com/pricing. The page does not say a free plan existed or ended; it simply has none, which is how a withdrawn free tier usually looks. |
| g2 | Holds. Free plan, "permanent (not a trial); no credit card required": 0.5 GB per project, 100 CU-hours per project, compute scales to zero after 5 minutes idle and that "cannot be turned off". Running out of compute suspends it until the next period; passing storage blocks writes; "None of these limits delete your data." | https://neon.com/pricing (neon.tech now redirects to neon.com) |
| g3 | Holds, with limits the claim leaves out: 500 MB database per project, 2 active projects, and "Free projects are paused after 1 week of inactivity." The pricing page did not say whether a card is required. | https://supabase.com/pricing. The card question is not settled there; the learner should say where else on Supabase's own site they would look, or that they would find out at sign-up. |
| g4 | Holds in part. Static sites are free. A free web service gets 750 instance hours a month per workspace, spins down after 15 minutes without traffic and takes about a minute to come back; past the hours, services are suspended until the month ends. "Ample" is a judgment the page can't settle; the sleep is what the claim leaves out. | https://render.com/docs/free |
| g5 | Holds, with the consequence left out. Render's docs: "Free Render Postgres databases expire 30 days after creation. An expired Free database is inaccessible unless you upgrade it to a paid compute plan." and "After the grace period, Render deletes the database (along with all of its data)." The grace period is 14 days. Render's changelog dates the 30-day rule to 2024-05-20 (it was 90 days before), so the sentence was accurate in fall 2025 and still is. What it hides is the deletion: "only free for the first month" reads as "then you pay", when it is "then it's locked, and two weeks later it's gone with your data, unless you pay". (Odin's lesson, read in orientation, says the lowest Render databases cost $7, which is a different way of telling only part of the same fact.) | https://render.com/docs/free; the date from https://render.com/changelog/free-postgresql-instances-now-expire-after-30-days-previously-90 |
| g6 | Holds, as a statement about signing up: see g2. Included because it carries no detail at all, so the learner has to decide what "free account" would need to mean before it can be checked. | https://neon.com/pricing |

What to draw out at the end: the pricing page settles whether a free tier exists and its headline
limits; the docs page on the free plan settles sleep and what happens past a limit; whether a card
is asked for is often on neither. Render's own free docs say, of bandwidth: "If you consume all of
your outbound bandwidth during a given month, Render bills you for a supplementary amount. If you
haven't added a payment method, Render instead suspends all of your Free services for the
remainder of the month." That is the risk of having a card on file, stated by the vendor, without
saying whether a card is needed to sign up. Where a vendor's pages don't settle a claim, the honest answer is "I'd find out at sign-up",
not a blog post's word for it. And an absence (g1) is evidence only once you are sure you are on
the page that would list the plan if it existed.
