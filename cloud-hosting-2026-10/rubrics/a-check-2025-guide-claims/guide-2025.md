Checked against the vendors' own pages on 2026-10-01 (Neon's storage figure re-read on
2026-10-02). **Vendors change these pages: before ruling on any question, re-open its settling page
and confirm it still says what is quoted. If it doesn't, the page wins and this key is wrong for
that question.**

Scenario note: `g2` and `g6` are both settled on Neon's pricing page. If `g2` has been served,
`g6` is mostly about deciding what a vague claim would have to mean before it can be checked, so
put the weight there. Neon's storage went from 0.5 GB to 1 GB per project overnight on 2026-10-02.
Neither claim states a figure, so neither is stale; the change is still worth mentioning as an
example of how fast these limits move.

What holds for every question: full credit is the criterion applied to this one claim, the
settling sentence found on the vendor's own current page and the verdict right. Opening a deep
link to the vendor's page and reading the sentence there counts; a search snippet, a comparison
article, a forum or the agent does not. The pricing page settles whether a free tier
exists and its headline limits; the docs page on the free plan settles sleep and what happens past
a limit; whether a card is asked for is often on neither. Render's own free docs say, of bandwidth:
"If you consume all of your outbound bandwidth during a given month, Render bills you for a
supplementary amount. If you haven't added a payment method, Render instead suspends all of your
Free services for the remainder of the month." That is the risk of a card on file, stated by the
vendor, without saying whether one is needed to sign up. An absence (`g1`) is evidence only once
the learner is sure they are on the page that would list the plan if it existed. None of the six
is a limit changed since 2025.

### g1

- **goal:** `c-check-vendor-claims`
- **answer:** gone, and already gone when the guide was written. PlanetScale's pricing page,
  https://planetscale.com/pricing, lists no free plan; the cheapest listed option was a $5/month
  Postgres single node, and it now sells Postgres as well as MySQL (Vitess). Its changelog,
  https://planetscale.com/changelog/hobby-deprecated, and its FAQ,
  https://planetscale.com/docs/plans/hobby-plan-deprecation-faq, say the free Hobby plan ended
  April 8, 2024, with no new Hobby databases after March 6, 2024. The pricing page doesn't say a
  free plan existed or ended; it simply has none, which is how a withdrawn free tier usually looks.
- **credit:** full for "gone", with the settling sentence found on a PlanetScale page (pricing
  page, changelog or FAQ). Half for a PlanetScale page found but the verdict hedged ("probably
  gone"). None for "gone" resting on anything but PlanetScale's pages.
- **tutor note:** ask how sure they are that the pricing page is the page that would list a free
  plan if there were one.

### g2

- **goal:** `c-check-vendor-claims`
- **answer:** holds. Neon's pricing page, https://neon.com/pricing (neon.tech redirects there):
  the Free plan is "permanent (not a trial); no credit card required", storage "1 GB/project, 20 GB
  account total" (0.5 GB on 2026-10-01), 100 CU-hours per project, compute that scales to zero
  after 5 minutes idle and "cannot be turned off". Running out of compute suspends it until the
  next period; passing storage blocks writes; "None of these limits delete your data." Branching
  holds too: the pricing page says "All plans include: ... database branching", and the Free plan
  allows 10 branches per project.
- **credit:** full for "holds", with the settling sentence found on Neon's pricing page and the
  verdict covering every part of the claim a page can settle (Postgres, free tier, branching).
  Half for Neon's page found but the verdict hedged or wrong, or leaving a part out. None for "holds" resting on another source.
- **tutor note:** the storage figure changed overnight on 2026-10-02; worth saying as an example of
  how fast these move.

### g3

- **goal:** `c-check-vendor-claims`
- **answer:** holds: Supabase's pricing page, https://supabase.com/pricing, lists a free plan
  (500 MB per project, 2 active projects, "Free projects are paused after 1 week of inactivity").
- **credit:** full for "holds", with the settling sentence found on Supabase's pricing page. Half
  for Supabase's page found but the verdict hedged or wrong. None for "holds" resting on another
  source.
- **tutor note:** if they raise a card: the pricing page doesn't say; Supabase's billing docs say
  "Paid plans require a credit card to be on file" and nothing about the free plan; a dated 2021
  Supabase blog says sign-up needs no card, which shows "no card then", not "no card today".

### g4

- **goal:** `c-check-vendor-claims`
- **answer:** holds as far as it can be checked: Render's free docs, https://render.com/docs/free,
  say static sites are free and a free web service gets 750 instance hours a month per workspace.
  "Ample" is a judgment the page can't settle.
- **credit:** full for "holds", with the settling sentence found on Render's docs. Half for
  Render's docs found but the verdict wrong, or "can't be checked" for the whole claim. None for
  a verdict resting on another source.
- **tutor note:** if they stop on "ample", ask which part of the claim a page could settle.

### g5

- **goal:** `c-check-vendor-claims`
- **answer:** holds. Render's free docs: "Free Render Postgres
  databases expire 30 days after creation. An expired Free database is inaccessible unless you
  upgrade it to a paid compute plan." and "After the grace period, Render deletes the database
  (along with all of its data)." The grace period is 14 days. Render's changelog,
  https://render.com/changelog/free-postgresql-instances-now-expire-after-30-days-previously-90,
  dates the 30-day rule to 2024-05-20, so the sentence was accurate in fall 2025 and still is. It
  hides the deletion: "only free for the first month" reads as "then you pay", when it is "then it's
  locked, and two weeks later it's gone with your data, unless you pay".
- **credit:** full for "holds", with the 30-day sentence found on Render's docs. Half for Render's
  docs found but the verdict "changed" or "gone". None for a verdict resting on another source.
- **tutor note:** "free for a month" and "deleted after a month unless you pay" are different
  risks; ask which the guide's reader would have expected.

### g6

- **goal:** `c-check-vendor-claims`
- **answer:** holds, as a statement about signing up: Neon's Free plan is "permanent (not a trial);
  no credit card required", 1 GB per project, compute that scales to zero after 5 minutes idle. It
  carries no detail, so the learner first has to say what "a free account" must mean.
- **credit:** full for "holds" once they have said what it must mean (permanent, no card, how big,
  whether it sleeps) and checked that on neon.com, or for "too vague" if they then make it
  checkable in those terms and check it, in either case with the settling sentence found on
  neon.com. Half for "holds" with no meaning stated, or "too vague" left unchecked.
- **tutor note:** if `g2` has been served, put the weight on deciding what a vague claim would have
  to mean before it can be checked.
