Sources checked as resolving, and Render's pages read, on 2026-10-01 (the forum's sunset notice on
2026-10-02). Re-open any vendor page named here before ruling on its question; if it has changed,
the page wins.

Only `s1` settles the claim: it is the vendor's own current page about exactly this, and on it the
sleep half holds and the Postgres half is false (free Postgres expires 30 days after creation and
is deleted after a 14-day grace period). For every other source, either non-settling verdict
("helps with what to look for" or "doesn't help") passes with the right reason, except `s3`, where
only "doesn't help" passes: asking the agent whether it is sure does not count. Where a source
doesn't settle the claim, the right place to go instead is Render's own free-plan docs. The prompt
sentence earns credit when it would make an agent link the vendor's own page for each claim rather
than a comparison article; from the second question on, it is a revision of the last one.

### s1

- **goal:** `c-check-vendor-claims`
- **answer:** settles it: Render's own current docs on the free plan. The sleep half holds
  ("Render spins down a Free web service that goes 15 minutes without receiving any inbound
  traffic"); the Postgres half is false ("Free Render Postgres databases expire 30 days after
  creation", deleted after a 14-day grace period).
- **credit:** full for "settles it", with the reason (the vendor's own page on this), and the
  30-day expiry found on opening it. Half for "settles it" without finding the expiry.

### s2

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: Render's own page, but it has no spin-down or Postgres-expiry
  wording. Go to Render's free-plan docs instead.
- **credit:** full for a non-settling verdict with the reason that the page doesn't address the
  claim, and the free-plan docs named instead. Half for the verdict with "it's a pricing page" and
  no more, or with nowhere better named.
- **tutor note:** "does the pricing page say what happens when the service is idle, or when the
  database is a month old?" If `s9` was served before, ask why one of Render's own pages might
  settle it and the other not.

### s3

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't help: the agent again, saying the same thing with more confidence. Go to
  Render's own free-plan docs.
- **credit:** full for "doesn't help", with the reason that re-asking the agent is not checking,
  and the vendor's docs named instead. Half for "doesn't help" with no reason. None for "helps with
  what to look for".
- **tutor note:** "where would its answer have come from?"

### s4

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: dated and secondary, and its Render paragraph contradicts itself
  on databases (both "$7" and "expires 30 days"). Go to Render's free-plan docs.
- **credit:** full for a non-settling verdict with the reason that it is not Render and not
  current, and the vendor's docs named instead. Half for the verdict with only one of those
  reasons.
- **tutor note:** "when was this true?" The learner probably skimmed only the first line of each
  vendor; if they judge it without opening it, tell them the paragraph says both, then ask.

### s5

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: a vendor's article about other vendors, with an interest in what
  you choose, and only as current as its last update. Go to Render's free-plan docs.
- **credit:** full for a non-settling verdict with the reason that it isn't Render's page (and,
  credited but not required, that its author sells hosting), and the vendor's docs named instead.
  Half for the verdict with no reason.
- **tutor note:** "whose page is it, and what does it want you to choose?"

### s6

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: careful and dated, but secondary; true as of 2026-09-16 at best,
  and nobody would update it the day Render changed. Go to Render's free-plan docs.
- **credit:** full for a non-settling verdict with the reason that it is not the vendor's own
  current page, and the vendor's docs named instead. Half for the verdict resting only on the
  affiliate links.
- **tutor note:** "when was this true, and who would know if it changed yesterday?"

### s7

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: on Render's site, but users talking, not Render, and from 2024. The
  forum itself was shut: community.render.com now redirects to https://render.com/docs/community,
  which says "The community forum was sunset on March 24, 2026". Go to Render's free-plan docs.
- **credit:** full for a non-settling verdict with the reason that it isn't the vendor speaking
  (or that it is old), and the vendor's docs named instead. Half for the verdict with no reason.
- **tutor note:** "it's on Render's site; is it Render saying it?" Afterwards, say the forum has
  since been shut and its threads are stranded at the date they were written.

### s8

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: recent and first-hand, but one account on one day, and nobody's
  database is 30 days old after a week. Go to Render's free-plan docs.
- **credit:** full for a non-settling verdict with the reason that a week's experience can't show
  a 30-day rule (or that it is one account, not the vendor), and the vendor's docs named instead.
  Half for the verdict with no reason.
- **tutor note:** "what could they have seen in a week?"

### s9

- **goal:** `c-check-vendor-claims`
- **answer:** doesn't settle it: Render's own page, but about something else, its MCP server. It
  matters for whether an agent can reach the host, which belongs to weighing plans. Go to Render's
  free-plan docs.
- **credit:** full for a non-settling verdict with the reason that it is not about this claim, and
  the free-plan docs named instead. Half for the verdict with no reason.
- **tutor note:** "it's Render's own page; is it about this claim?"
