Checked against the vendors' own pages on 2026-10-01 (Neon's storage figure re-read on
2026-10-02). **Vendors change these pages: before ruling on any question, re-open its settling page
and confirm it still says what is quoted. If it doesn't, the page wins and this key is wrong for
that question.**

What holds for every question: full credit always includes naming the kind of page that settled
it (pricing page, free-plan docs, billing docs, changelog, trial page), or saying the vendor's
pages couldn't. The verdict must rest on a sentence from the vendor's own current
page, not a search snippet, a comparison article, a forum or the agent; or on an honest "the
vendor's pages don't settle this" after looking. The pricing page settles whether a free tier
exists and its headline limits; the docs page on the free plan settles sleep and what happens past
a limit; whether a card is asked for is often on neither. Render's own free docs say, of bandwidth:
"If you consume all of your outbound bandwidth during a given month, Render bills you for a
supplementary amount. If you haven't added a payment method, Render instead suspends all of your
Free services for the remainder of the month." That is the risk of a card on file, stated by the
vendor, without saying whether one is needed to sign up. An absence (`g1`) is evidence only once
the learner is sure they are on the page that would list the plan if it existed. The prompt
sentence earns credit when it would make an agent give, for each claim, the vendor's own page (and
ideally the date of its information); from the second question on, it is a revision of the last
one. None of the six is a limit changed since 2025.

### g1

- **goal:** `c-check-vendor-claims`
- **answer:** gone, and already gone when the guide was written. PlanetScale's pricing page,
  https://planetscale.com/pricing, lists no free plan; the cheapest listed option was a $5/month
  Postgres single node, and it now sells Postgres as well as MySQL (Vitess). Its changelog,
  https://planetscale.com/changelog/hobby-deprecated, and its FAQ,
  https://planetscale.com/docs/plans/hobby-plan-deprecation-faq, say the free Hobby plan ended
  April 8, 2024, with no new Hobby databases after March 6, 2024. The pricing page doesn't say a
  free plan existed or ended; it simply has none, which is how a withdrawn free tier usually looks.
- **credit:** full for "gone", resting on any PlanetScale page that settles it (pricing page,
  changelog or FAQ), with the kind of page named and a prompt sentence asking for the vendor's page
  per claim. Half for "gone" resting on something other than PlanetScale's pages, or with no prompt
  sentence.
- **tutor note:** ask how sure they are that the pricing page is the page that would list a free
  plan if there were one.

### g2

- **goal:** `c-check-vendor-claims`
- **answer:** holds. Neon's pricing page, https://neon.com/pricing (neon.tech redirects there):
  the Free plan is "permanent (not a trial); no credit card required", storage "1 GB/project, 20 GB
  account total" (0.5 GB on 2026-10-01), 100 CU-hours per project, compute that scales to zero
  after 5 minutes idle and "cannot be turned off". Running out of compute suspends it until the
  next period; passing storage blocks writes; "None of these limits delete your data." Left out:
  the sleep, and the limits.
- **credit:** full for "holds", resting on Neon's pricing page, with at least one thing the claim
  leaves out (the sleep, or a limit) and a prompt sentence. Half for "holds" with nothing it leaves
  out, or resting on another source.
- **tutor note:** the storage figure changed overnight on 2026-10-02; worth saying as an example of
  how fast these move.

### g3

- **goal:** `c-check-vendor-claims`
- **answer:** holds, with limits left out: Supabase's pricing page, https://supabase.com/pricing,
  gives 500 MB per project, 2 active projects, and "Free projects are paused after 1 week of
  inactivity." The pricing page did not say whether a card is required. Supabase's billing docs say
  "Paid plans require a credit card to be on file" and nothing about the free plan; a 2021 Supabase
  blog post says you can sign up without a card. The blog is the vendor's own page but dated, so it
  supports "no card then", not "no card today".
- **credit:** full for "holds", resting on Supabase's pricing page, with the pause or a limit named
  as left out, a prompt sentence, and the card handled either way: "the vendor's pages don't settle
  it today; I'd find out at sign-up", after looking beyond the pricing page, earns full credit, as
  does the 2021 blog read as "no card then". Half for the card taken from a third-party blog or the
  agent, or the 2021 blog read as "no card today", or nothing left out named.
- **tutor note:** if they cite Supabase's 2021 blog, ask what it shows about today. If they say
  "I'd find out at sign-up", ask where on Supabase's site they looked first.

### g4

- **goal:** `c-check-vendor-claims`
- **answer:** holds, with the sleep left out ("ample" can't be checked). Render's free docs,
  https://render.com/docs/free: static sites are free; a free web service gets 750 instance hours a
  month per workspace, spins down after 15 minutes without traffic and takes about a minute to come
  back; past the hours, services are suspended until the month ends.
- **credit:** full for "holds", resting on Render's docs, with the spin-down named as left out and
  a prompt sentence. Half for "holds" with the spin-down missed, or for a verdict resting on
  another source.

### g5

- **goal:** `c-check-vendor-claims`
- **answer:** holds, with the consequence left out. Render's free docs: "Free Render Postgres
  databases expire 30 days after creation. An expired Free database is inaccessible unless you
  upgrade it to a paid compute plan." and "After the grace period, Render deletes the database
  (along with all of its data)." The grace period is 14 days. Render's changelog,
  https://render.com/changelog/free-postgresql-instances-now-expire-after-30-days-previously-90,
  dates the 30-day rule to 2024-05-20, so the sentence was accurate in fall 2025 and still is. It
  hides the deletion: "only free for the first month" reads as "then you pay", when it is "then it's
  locked, and two weeks later it's gone with your data, unless you pay".
- **credit:** full for "holds", resting on Render's docs, with the deletion after the grace period
  found and a prompt sentence. Half for "holds" without the deletion, or "changed" with the
  deletion found.
- **tutor note:** "free for a month" and "deleted after a month unless you pay" are different
  risks; ask which the guide's reader would have expected.

### g6

- **goal:** `c-check-vendor-claims`
- **answer:** holds, as a statement about signing up: Neon's Free plan is "permanent (not a trial);
  no credit card required", 1 GB per project, compute that scales to zero after 5 minutes idle. It
  carries no detail, so the learner first has to say what "a free account" must mean.
- **credit:** full for "holds" once they have said what it must mean (permanent, no card, how big,
  whether it sleeps) and checked that on neon.com, or for "too vague" if they then make it
  checkable in those terms and check it; with a prompt sentence. Half for "holds" with no meaning
  stated, or "too vague" left unchecked.
- **tutor note:** if `g2` has been served, put the weight on deciding what a vague claim would have
  to mean before it can be checked.
