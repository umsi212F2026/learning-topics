Must name, for this app (about twenty users, a class project): **sleep** (Harbor's server sleeps
after 15 minutes idle and the next visitor waits about a minute; Kettle's never sleeps); **past a
limit** (Kettle's credit lasts about three weeks, so its server stops in the last week of the
month, grading week, unless a card is on file, and then it bills; Harbor's server doesn't stop);
**card** (none of the three requires one; one on file turns a stop or pause into a bill on Harbor,
for bandwidth, and on Kettle, for credit; Brightpage can't bill); **agent access** (Harbor gives one
tool for both parts; Plan S needs two, so two sets of credentials); **moving** (easy from both:
ordinary npm and Node, plain files); **what the extra vendor adds** (a second account, Kettle's
address copied into the frontend's build, agent credentials on each, two dashboards and log places).

Present but not deciding for twenty users, and never a miss when left out: Harbor's 750-hour limit
(one web service all month is about 730 hours); the 100 GB bandwidth lines; Brightpage having no
request logs (it runs no code); Kettle's `kettle.toml`. Leaning on one is fine if what is said
matches the terms. A claim the terms contradict is a miss; "nothing in the terms says this" is
enough to name one that is merely unsupported. Remarks about where the database goes are neither
credited nor counted.

### v1

- **goal:** `c-weigh-hosting-plans`
- **answer:** either plan, with every must-name difference, what the extra vendor adds, nothing the
  terms don't support, and a real case for the other plan. For H, for instance: Kettle stops in
  grading week unless a card is on file, and then bills; Harbor sleeps but doesn't stop; no card
  needed anywhere, and one on Harbor or Kettle turns a stop into a bill, while Brightpage can't
  bill; one agent tool against two; moving easy either way; S adds a second account, Kettle's
  address in the build, two sets of credentials and two places to look. Case for S: nothing ever
  sleeps, and Brightpage can never bill.
- **credit:** full for every must-name difference, the extra vendor's cost, nothing unsupported,
  and a strongest case for the other plan that comes from the terms. Half for all but one
  must-name item, or a case for the other plan that is only "it's simpler" or "it never sleeps"
  with nothing else. The choice itself earns nothing either way.

### v2

- **goal:** `c-weigh-hosting-plans`
- **answer:** Harbor's server never stops, while Kettle's stops in grading week unless a card is on
  file; one account and one agent tool for both parts; nothing to copy between vendors; with no
  card on file, nothing on Harbor can bill. Its cost, a minute's wait after 15 idle minutes, is
  the one the student already named.
- **credit:** full for a case built from at least three terms (no stop, one account or one tool,
  nothing copied between vendors, no card means no bill), with nothing unsupported. Half for one
  or two of those, or for a case that rests on "simpler" alone.
- **tutor note:** partner of `v1`. If `v1` was served before, ask how this case compares with the
  one they gave there for the plan they didn't choose.

### v3

- **goal:** `c-weigh-hosting-plans`
- **answer:** "free forever" and "never charges anything" are not supported: with a card on file,
  Harbor bills bandwidth past 100 GB a month. The terms say no card is needed, and without one
  Harbor suspends rather than bills. The two accounts point is right.
- **credit:** full for both claims named as unsupported and the card on file named as what lets
  Harbor bill. Half for the claims named with no line from the terms, or for one of the two.

### v4

- **goal:** `c-weigh-hosting-plans`
- **answer:** two sets of agent credentials and two tools instead of Harbor's one; Kettle's address
  copied into the frontend's build; two dashboards and places to look when something breaks.
- **credit:** full for at least two of those three, with the agent's second tool or credentials
  among them. Half for one.

### v5

- **goal:** `c-weigh-hosting-plans`
- **answer:** faster, more reliable and more secure appear nowhere in the terms. Missed: Kettle's
  server stops in grading week unless a card is on file, which is the difference that matters
  most against Harbor's sleep.
- **credit:** full for all three reasons named as unsupported and Kettle's stop named as the
  missed difference. Half for the unsupported reasons alone, or for Kettle's stop alone. Another
  must-name item (the card, moving, the address copied into the build) also counts as a miss
  named, in place of Kettle's stop.

### v6

- **goal:** `c-weigh-hosting-plans`
- **answer:** no vendor needs a card to sign up; the terms say so in their first line. A card on
  file is a risk, not a requirement: on Harbor it lets bandwidth past 100 GB be billed, on Kettle it
  keeps the server running past the credit and bills; Brightpage can't bill at all.
- **credit:** full for the first line of the terms named as contradicting the claim, and the card
  risk stated for Harbor and Kettle. Half for one of the two.
- **tutor note:** partner of `v2` and `v1`. If either was served, ask what each said about a card.

### v7

- **goal:** `c-weigh-hosting-plans`
- **answer:** the strongest case for Plan S: nothing in it ever sleeps, so no grader waits a minute;
  Brightpage can never bill. Also missing: whether a card is required (none is), and moving (easy
  either way).
- **credit:** full for a case for S from the terms (no sleep, and Brightpage can't bill, or another
  term-based reason) plus the card requirement. Half for the case alone, or for the missing items
  without the case.

### v8

- **goal:** `c-weigh-hosting-plans`
- **answer:** yes: a ping every ten minutes beats the 15-minute sleep, and one service awake all
  month is about 744 hours, under Harbor's 750, so nothing is suspended and, with no card on file,
  nothing is billed. It costs nothing in these terms, though it leaves only a few hours' margin.
- **credit:** full for "supported" with both reasons (ten minutes is under 15, and the hours stay
  under 750). Half for "supported" with one reason. None for "unsupported", which the terms
  contradict.
