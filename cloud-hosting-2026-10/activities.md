# Activities: cloud hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

In this topic's banks and live questions, a made-up vendor name stands for one vendor, with one
offer and one set of terms, everywhere in the topic, and a new scenario or live instance invents
names not used anywhere else in it. The names in use: in `crumbs` (`a-place-described-plan`),
Brightpage, Kettle, Flintlet and Harbor; in `quayline-emberbox` (`a-weigh-described-plans`),
Quayline, Lanternhost and Emberbox; in `a-words`, Driftwell (`w-free-tier`) and Copperstack
(`w-lock-in`). Learner-facing text states the task, never the scoring; a setup may say what the
plans or terms contain and that something, like the database, is outside them.

## Check notes

2026-10-01. In both checks for placing parts and both checks for weighing plans, the tutor writes
the vendors' offers and terms, already distilled, for the learner. In the checks for vendor claims,
the learner looks up one claim at a time on the vendor's own pages, or judges one source against
one claim, so reading a real vendor's pricing, docs and billing pages unaided is examined one
claim at a time, never across a whole agent's answer. Each entry's `doesn't show` admits its own
part of this.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-place-app-parts` | say which kind of host the frontend and the backend each need, and whether a hosting plan covers them | Given an app with a React frontend and an Express backend, and a hosting plan listing each vendor and what it offers, says which part each vendor would host, and names any part the plan leaves without a host or puts on a host that cannot run it, or says both are covered. It passes when every gap and mismatch is found and nothing is named that isn't one, including for a plan where one vendor hosts both, or where the backend serves the built frontend itself. Where the database is kept is not part of it. |
| `c-check-vendor-claims` | find out whether what an agent says about a hosting vendor is true today | Given a claim an agent made about a hosting vendor's free tier, finds on the vendor's own current pages the sentence that settles it, and says whether the claim still holds. Opening a deep link the agent gave to the vendor's page, and reading the sentence there, counts. Taking the agent's word for it, or a blog post's or a forum's, does not meet it, and neither does asking the agent whether it is sure. |
| `c-weigh-hosting-plans` | choose between hosting plans for an app, knowing what each would cost | Given two hosting plans for an app's frontend and backend, one putting both with a single vendor and one using a separate vendor for each, and each vendor's free-tier terms, says for each plan whether the app sleeps when idle, what happens when it passes a limit, and whether a credit card is required and what having one on file risks; says whether their agent can reach every host to change its settings and read its logs, and what it can't do there; says what the extra vendor adds in accounts, secrets and places to look when something breaks, and how hard each plan would be to move to another vendor; and chooses one and states the strongest case the terms give for the plan they didn't choose. It passes when each of these is stated as the terms give it, the case for the other plan rests on a difference that matters for a class project with few users, and nothing is named that the terms don't support. Which plan they choose is not part of it, and neither is where the database is kept. |

## Coverage

<!--
  Derivation convention: an activity whose `serves` is `all` sits on the `o-orientation` row
  only.
-->

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-odin-deployment` | |
| `c-place-app-parts` | `a-place-described-plan`, `a-place-lab-plan` | |
| `c-check-vendor-claims` | `a-check-2025-guide-claims`, `a-sort-claim-sources`, `a-check-lab-answer` | Every check here is one claim at a time: `a-check-2025-guide-claims` on a claim from an old guide, `a-sort-claim-sources` on one source judged against a fixed claim, `a-check-lab-answer` on one claim from the learner's own agent. None asks the learner to find the claims worth checking in a whole answer. |
| `c-weigh-hosting-plans` | `a-weigh-described-plans`, `a-weigh-lab-plans` | |

---

## Activities

### `a-read-odin-deployment`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** two free pages, no account, read in this order as one sitting. Both checked
  2026-10-01.
  1. **Read first:** MDN Web Docs, "What is a web server?",
     https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/What_is_a_web_server
     (last modified Apr 29, 2025). Read only Summary (about 365 words) and Static vs. dynamic
     content (about 260): about 625 words, no code. Skip Deeper dive's opening, Hosting files,
     Communicating through HTTP and Next steps. What it gives that Odin doesn't: the static web
     server, which "sends its hosted files as-is to your browser", as against the dynamic one with
     an application server and a database.
  2. **Then:** The Odin Project, "Deployment" (Node path),
     https://www.theodinproject.com/lessons/node-path-nodejs-deployment, down to, and not
     including, the heading "Debugging and troubleshooting deployments". Read in full: What are
     hosting providers?, Static vs dynamic sites, What is a PaaS?, and under How do PaaS services
     work? the Instances and Server instance and database instance parts (about 700 words). Skim:
     Databases and Domain names (first paragraph of each), and Our recommended PaaS services, read
     for the shape, not the numbers: the first line of each vendor ("Can deploy both servers and
     databases", "Can deploy databases only"). Skip Keep your secrets safe!, Debugging and
     troubleshooting deployments, the Assignment and Additional resources.
  About 1,300 words read and a skim: 10 to 11 minutes of reading, 15 minutes with the two stops.
  Words in place: deploy, static, server, database, free tier (Heroku's, ended 2022), instance,
  domain, and, in the skimmed vendor lists, sleep and credit card. The rest of the fifteen have
  their own supply; glossing them as they come up is optional. Odin is written for its own Node
  course, whose apps are rendered on the server, so its picture is two boxes (a server and a
  database) and it says Netlify and Vercel are "not the right tools for our back ends" without
  saying where a React frontend would go. MDN's static web server is the third box, which is why it
  comes first.
- **verified:** 2026-10-02
- **learner does:** reads MDN first, with their Problem Set 2 app's folder open beside the page,
  then Odin. Stops twice and answers before reading on; "I don't know yet" is an honest answer:
  1. Odin, after Server instance and database instance: **sketches their own app as three boxes,
     frontend, backend and database, and labels the frontend and backend boxes with the kind of
     host each needs** (one that sends files as they are, or "sent by the Express server itself";
     one that keeps a program running). The database box is marked "see database-hosting" rather
     than placed.
  2. Odin, after skimming the vendors: picks one that can deploy servers, says whether it could
     hold their frontend or backend box,
     and names one thing in its paragraph they would check on the vendor's own site before relying
     on it.
  Then the close, about 5 minutes, with the sketch and the reading still beside them: two quick
  rehearsals, neither judged, each answered in a sentence. First, the tutor describes a made-up
  app's frontend and backend and one vendor's offer in a line, and the learner says which part
  that vendor could host, or none. Second, the tutor gives one line of terms from each of two
  plans, and the learner says one difference between them that would matter for a class project.
  Then answers the question the tutor puts: with your sketch and the reading beside you, could you
  now attempt these three things for real: saying which kind of host an app's frontend and backend
  each need and whether a plan covers them; finding out whether what an agent says about a hosting
  vendor is true today; and choosing between two hosting plans knowing what each would cost you?
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you said the frontend needs a server host because it's React; once it's built, what
  is left in `dist/` that has to run on the host?"). At stop 1, checks the built frontend is on a
  host that sends files and the Express server on one that keeps it running; if the learner tries
  to place the database, says that belongs to the database-hosting topic. **Flags Odin's lagging vendor details if the learner stops on one, without
  dropping the page:** as checked 2026-10-01, Railway's trial is a one-time $5 for up to 30 days,
  then a Free plan with $1 of free credit a month; Render's free Postgres (Odin says both "$7" and "expires 30
  days") expires after 30 days and is deleted 14 days later; Neon's compute now scales to zero
  after 5 minutes idle; Aiven's free service is 1 GB and powers off when idle, still with no card.
  Says secrets, backups and debugging are later topics. Makes no change to the learner's app. At
  the close, sets the two rehearsals from the generator below and grades neither; if an answer
  shows a misunderstanding (the frontend needing a server host because it is React; "free" as the
  only difference worth naming), explains it once and moves on. Then puts the readiness question
  as written above and rules on the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops,
  the rehearsals, or whether the tutor thinks they are ready. A plain yes to all three parts is
  `criterion: met`. A hedge on any part, with no plain no, is `criterion: unclear`: explain the
  hedged part once more and put the question again; a second hedge stays `unclear`, and the tutor
  offers an activity on that capability. A plain no to any part is `criterion: not met`: record it,
  ask what is missing, and offer to go back over the stops that bear on the capability named, or an
  activity on it; don't put the question again in the same sitting. This goal isn't required, so a
  no never blocks anything else the learner wants to try.
- **generator:** vary the made-up app and the two rehearsal items; hold the rest fixed. The app is
  small, with a React frontend and an Express server, used by a class (a study-group finder, a club
  sign-up sheet, a recipe box, a used-textbook board). Rehearsal one is one plan line from
  `a-place-described-plan`'s generator at Easy: one vendor, one offer, one part, under a vendor
  name not on the topic's list of names in use. Rehearsal two is
  one dimension from `a-weigh-described-plans`'s generator (sleep, past a limit, card, agent
  access, or moving), one line per plan, at Easy. Fixed: the reading and its two stops, then two
  rehearsals in that order, neither graded, then the readiness question word for word.
  Difficulty doesn't vary: this settles an indication, not a capability.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about any of the three capabilities: the stops and rehearsals are helped, ungraded
  and of the easiest kind, a one-sentence answer never has to be complete, and claim checking is
  rehearsed only at the second stop. It shows nothing about the fifteen words, which have their
  own supply.
- **offer as:** this topic's orientation, deliberately one entry holding a sequence: two sections
  of a short MDN page that supply the static web server, then the first half of Odin's lesson,
  which supplies hosting providers, PaaS, instances and four real vendors, skimmed, then a short
  close where you say whether you have the shape. About 20 minutes: 15 for the reading and its
  stops, 5 for the close. Odin's vendor numbers are a year or so behind in places, and the tutor
  flags them if they come up; that is part of the lesson, not a defect in the choice.
- **check note:** At stop 1, a frontend labeled "sent by the Express server itself" passes the check
  as well as one on a host that sends files: some Problem Set 2 apps already serve `dist/` from
  Express, and that arrangement is covered under `c-place-app-parts`. Don't steer the learner off
  it.

### `a-place-described-plan`

- **serves:** `c-place-app-parts`
- **supports:** attempt
- **checks:** `c-place-app-parts`
- **artifact:** no external source. A made-up app and hosting plan, written by the tutor per the
  generator below. 10 minutes.
- **verified:** 2026-10-01
- **learner does:** reads the app's parts and the plan, then writes alone, for each vendor, which
  part it would host, and then names every part left without a host or put on a host that cannot
  run it, or says there are none. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and writes the key into the record before
  showing anything: which part each vendor hosts, and every gap and mismatch, or "both
  covered". Shows the app's parts and the plan. Waits, writing down any help word for word. Sends
  the adjudicator the parts, the plan, the key, the learner's answer verbatim and every piece of
  help. After the ruling, tells the learner what was missed or named wrongly. Labels the attempt
  with the question's path, or `a-place-described-plan/<shape>` when the generator is run live. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** criterion met with no help.
- **generator:** fixed: the app has a frontend and a backend, described in a short list in the
  form of `tasks/a-place-described-plan/crumbs.md` (what each part is and what it needs to run); the app's
  database is never part of the plan or the key. In what the learner sees, state the task, never the scoring: no criterion guard such as "and
  nothing that isn't one" or "name nothing the terms don't support". A setup may say what the plans
  or terms contain and that something, like the database, is outside them; it never tells the
  learner how they will be scored, and a remark about the database is the tutor's and the rubric's
  matter. The plan names one to three vendors, each with a
  one- or two-line offer written as that file writes them: what it hosts and runs, and what it does
  not. Vendors are made up, so the key depends only on the stated offers. A new scenario invents
  new vendor names on the same pattern, never one on the topic's list of names in use (at the head
  of this file), and never reproduces a `crumbs` plan. What
  varies: the app (a different one each attempt; its frontend is React or another framework built
  to static files, its backend Express or another long-running server), the vendors and their
  offers, and the plan's shape, each with the cases it carries:
  - `split-clean` (Easy; `all-covered`): one vendor per part, both covered.
  - `one-gap` (Easy; `gap`): one part left without a host.
  - `wrong-host` (Medium; `mismatch`): one part on a host that cannot run it as the app is now (a
    long-running server on a files-only or functions-only host).
  - `backend-serves` (Medium; `backend-serves`, with `all-covered`): the backend sends the built
    frontend itself and no static host is named, and both are covered. If the backend is on a host
    that cannot run it, the plan is set as two questions, one per case: one on the backend's host
    (`mismatch`), and a later one asking only whether the frontend's files reach the browser
    (`backend-serves`).
  - `shared-vendor` (Medium; `one-vendor-both`, with `all-covered`): one vendor hosts both parts as
    separate services, and both are covered. If one part is in that vendor's wrong service, the plan
    is set as two questions: one naming the faults (`mismatch`), and a later one asking only whether
    the vendor or the service chosen is at fault (`one-vendor-both`).
  A question carries one case a learner could get right or wrong on its own; never give half credit
  for one of two cases.
  - `decoy` (Hard; `all-covered`, with `backend-serves` or `one-vendor-both` as the variant has it):
    both covered, but the backend sends the built frontend itself and the frontend is also put on a
    static host, or a vendor hosting both has a limitation that doesn't bear on either part it was
    given (never a limitation about databases); either way it invites a false gap or mismatch.
  A plan never holds both a gap and a mismatch, since a learner could find one and miss the other
  under one ruling. Difficulty as marked. A scenario covers all five cases across its questions.
  For review visits, serve a case the learner hasn't passed, reading the labels `served.mjs`
  returns.
- **worked example:** work one Easy instance aloud: list what each part needs, then go vendor by
  vendor saying what it was given and whether its offer can do that job, and finish by checking
  each part has somewhere to live. For the backend sending the frontend itself, point to Full
  Stack Open part 3b, Serving static files from the backend,
  https://fullstackopen.com/en/part3/deploying_app_to_internet: `app.use(express.static('dist'))`
  makes the server send the built files, so no static host is needed. At the first level of help on
  a real attempt, ask only "what does each part need from a host?"
- **doesn't show:** the offers are stated plainly in a line each, so a pass doesn't show the
  learner could work out what a real vendor offers from its own pages, where the answer is spread
  over pricing and docs. Vendors are made up, so a pass says nothing about knowing which real
  vendor does what. Where the database is kept is left out, as the criterion says. The learner
  knows a check is on.
- **offer as:** the check that's available now: a made-up app and plan, 10 minutes, nothing to
  run, and the tutor picks the shape so the two cases the criterion names (one vendor hosting
  both, the backend serving the frontend) actually come up. `a-place-lab-plan` is the
  same capability on the plan your own lab prompt produced.

### `a-place-lab-plan`

- **serves:** `c-place-app-parts`
- **supports:** attempt
- **checks:** `c-place-app-parts`
- **artifact:** no external source. A hosting plan for the learner's own Problem Set 2 app, from
  an agent's answer to their table's session 11 lab prompt, and the parts of that app. By
  default the answer is a fresh rerun of the table's prompt or a tablemate's answer, chosen so
  that it names at least one vendor the learner has not signed up for or used in the lab; the
  learner's own lab answer is used only if it meets that too. 15 minutes, plus the tutor's
  preparation.
- **verified:** 2026-10-01
- **learner does:** gets from the tutor a list of their app's parts, and the plan with each
  vendor's offer stated in a line or two. Writes alone which part each vendor would host, and
  names every gap and mismatch, or says there are none. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, reads the learner's app (the learner need not see this) to
  list its parts as they are now: what the frontend builds to, whether the backend already sends
  the built frontend. The database is left out of the plan, the offers and the key; it belongs to
  the database-hosting topic. Turns the answer into a plan for the frontend and backend: if it already says which vendor hosts which part, uses that; if it is a
  comparison, takes the vendors it recommends and assigns each to the part the answer suggests it
  for; if the answer suggests nothing for some part, assigns one of the vendors it names to that
  part the way a student reading the answer plausibly would, and records that the tutor did this.
  For each vendor in the plan, reads that vendor's own current pages and writes its offer in a
  line or two, as `tasks/a-place-described-plan/crumbs.md` writes them, with the address and date of each
  page used, written from those pages that day; the offer must not be the agent's description of
  it, and a real functions host whose pages now say it runs an Express server unchanged is not a
  mismatch. If a vendor's pages don't settle
  whether it can run the part it was given, replaces it with another vendor the answer names whose
  pages do; if there is none, shows that part's line as "not judged: the vendor's own pages don't
  settle this", tells the learner to leave that part out, and leaves it out of the key, so the
  missing offer is never mistaken for a planted gap. Writes the key into the record from the
  offers. Any plan, faulted or not, can be ruled on. Waits during the attempt, writing down any help word for word. Sends the
  adjudicator the parts, the plan with its offers, the key, the learner's answer and every piece
  of help. Labels the attempt `a-place-lab-plan/<vendors, joined with +>`. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** criterion met with no help.
- **generator:** the material is whatever the learner's agent proposed, so no two instances match
  and nobody sets the difficulty. Hold fixed: offers come from the vendor's own pages on the day,
  never from the agent's answer; the key comes from those offers and the app's code. In what the learner sees, state the task, never the scoring: no criterion guard such as "and
  nothing that isn't one" or "name nothing the terms don't support". A setup may say what the plans
  or terms contain and that something, like the database, is outside them; it never tells the
  learner how they will be scored, and a remark about the database is the tutor's and the rubric's
  matter. The tutor
  records the cases the plan carries: `gap`, `mismatch` or `all-covered` by its verdict, plus
  `one-vendor-both` or `backend-serves` where the plan has them. A plan with both a gap and a
  mismatch is set as two questions, one on each part. Across visits, use a different agent answer each time (a tablemate's, or a fresh run of
  the lab prompt), preferring one that names a vendor the learner hasn't used.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "what does each part need from a host?", and the attempt is recorded `unaided: no`.
- **doesn't show:** the tutor writes the offers, so a pass doesn't show the learner could pull
  them out of a vendor's pages. Whether the plan exercises the hard cases (a shared vendor, a
  backend-served frontend) depends on what the agent proposed. The key rests on the tutor's
  reading of current vendor pages and of the app.
- **offer as:** the real thing: a plan from your table's own lab prompt, on vendors' real offers,
  checked against your own app. Any time after the lab; a fresh run of the prompt or a
  tablemate's answer keeps it new even after you've signed up. `a-place-described-plan` is the one
  to take before the lab.

### `a-check-2025-guide-claims`

- **serves:** `c-check-vendor-claims`
- **supports:** attempt
- **checks:** `c-check-vendor-claims`
- **artifact:** six sentences quoted exactly from the deployment guide given to students in this
  course's 2025 predecessor (SI 211), about PlanetScale, Neon, Supabase and Render, one per
  sitting, under a three-step procedure, checked against those vendors' own pages on 2026-10-01.
  One claim names a free tier that was already gone when the guide was written in fall 2025
  (PlanetScale's free Hobby plan ended April 8, 2024, with no new Hobby databases after March 6,
  2024).
  The rest hold: Render's Postgres "only free for the first month" was already the 30-day rule when
  written (Render's changelog dates it to May 2024). None is a limit that has changed since 2025. The guide itself is in the instructor's files and is not available to students, which is
  why its sentences are quoted. 10 to 15 minutes a sitting, with a browser.
- **learner does:** reads the procedure and the one claim served, then follows the three steps on
  it: says which page on the vendor's own site they expect to settle it and why; finds it and copies
  the sentence that settles it with its address and any date; and says whether the claim holds,
  has changed, or is gone.
- **tutor role:** critic
- **tutor does:** before the sitting, re-opens the settling page in the key for this claim and
  confirms it still says what is quoted; where it doesn't, the page wins and the tutor updates its
  own copy of the verdict. Shows the procedure and the one claim, never the key. Takes the learner's
  answers before commenting. If the verdict rests on something other than the vendor's page (a
  search result's snippet, a comparison article, the agent), asks where the vendor itself says
  that. On `g1`: an absence on a pricing page is evidence only once you're sure it's the page that
  would list the plan. On `g5`: "free for a month" and "deleted after a month unless you pay" are
  different risks. On `g6`, "holds" passes once the learner says what "a free account" must mean
  (permanent, no card, how big, whether it sleeps) and checks that on neon.com; "too vague" passes
  only if they then make it checkable that way and check it. If another claim has been served
  before, asks how the page that settled this one differs in kind from the one that settled that.
- **done when:** criterion met with no help, as it applies to this one claim: the learner's
  verdict rests on a quoted sentence from the vendor's own current page, or an honest "the
  vendor's pages don't settle this", and matches the key (for `g1`, gone; for `g6`, as above).
- **generator:** the claims are the guide's six real sentences, scenario `guide-2025`, questions
  `g1` to `g6`; nothing is invented, and no new scenario can be drafted without another real
  source of dated claims. Kinds of claim: withdrawn `g1`; holds but hides the consequence `g5`;
  holds `g2`, `g3`, `g4`; too vague to check as it stands `g6`. To pick the next, run
  `served.mjs cloud-hosting-2026-10 c-check-vendor-claims`, take a claim not yet served, and prefer
  a kind the learner hasn't met; `g1` and `g5` make the best first two. Once the learner has met
  Render's 30-day expiry anywhere in this topic, prefer claims about other vendors over `g5`. Stop
  when done when has been met on two or three sittings with different kinds, and offer
  `a-check-lab-answer`; using up the six is not the target.
- **worked example:** check a claim not in the six aloud, with a false start left in and named.
  For Fly.io's "only a short trial before pay-as-you-go": open the pricing page,
  https://docs.fly.io/about/pricing/, read "All organizations ... require a credit card on file"
  and nearly conclude a card is needed to sign up; then open the trial page,
  https://docs.fly.io/about/free-trial/, and find the fuller answer (no card to start, 2 hours of
  machine time or 7 days, and "adding a card ends the free trial"). Say what kind of page settled
  each part. At the first level of help on a real attempt, ask only "where would the vendor itself
  say that?"
- **doesn't show:** the claims come from an old guide rather than from the learner's own agent,
  and none is a limit changed since 2025, so a pass shows nothing about catching one. They are
  handed over one at a time rather than met inside an agent's answer. The six are fixed, so a
  later visit repeats a claim they have seen.
- **offer as:** real claims, from a real guide given to students in this course a year ago, some
  of them already stale when it was written, one at a time. You do the checking from the start, on real
  vendor pages, 10 to 15 minutes. The most hands-on of the checks, and the one that shows how fast
  this goes stale.

### `a-sort-claim-sources`

- **serves:** `c-check-vendor-claims`
- **supports:** attempt
- **checks:** `c-check-vendor-claims`
- **artifact:** no external source beyond the pages the sources name, all checked as resolving on
  2026-10-01. One fixed claim about Render's free tier and ten sources, one judged per sitting.
  10 minutes a sitting; 15 for `s1` and `s10`, which need a browser.
- **learner does:** hears the claim and the one source, and without opening it says: does this
  source settle the claim today, help only with knowing what to look for, or not help with this
  claim, and why. If it doesn't settle it, says where they would go instead. For `s1`, opens it
  and checks both halves of the claim on it; for `s10`, opens the link and does the same.
- **tutor role:** socratic questioner
- **tutor does:** takes the learner's verdict and reason before commenting. Asks this source's
  near-miss question from its tutor note rather than giving a verdict. For `s1`, makes sure the learner
  finds that the free Postgres expires after 30 days, so the second half of the claim is false. If
  another source has been served before, asks how this one differs from that one, and whether the
  verdict should differ too (for `s2` after `s9`, "both are Render's own pages; why might one of
  them settle it and the other not?").
- **done when:** the criterion as it applies to one source, met with no help: the learner rules
  rightly on whether this source settles the claim today (only `s1` does, and `s10` once its link
  to the vendor's own page is opened), with the right reason (whose page it is, whether it is current, whether it
  is about this claim). For `s2` and `s4` to `s9`, either non-settling verdict ("helps with what to
  look for" or "doesn't help") passes with the right reason; for `s3` only "doesn't help" passes,
  since asking the agent whether it is sure does not count; where it doesn't settle it, they named
  the vendor's own current docs as where to go instead; for `s1` and `s10`, they found the 30-day
  expiry on the page.
- **generator:** the claim is fixed: "Render's free web services sleep after 15 minutes and its
  free Postgres is free for good." The sources are scenario `render-claim`, questions `s1` to `s10`,
  each with its verdict and near-miss question in the key; nothing is invented. Kinds of source:
  settles it `s1`; the agent's deep link to the vendor's page, which settles it once opened, `s10`;
  vendor's own page not about this claim `s2`, `s9`; on the vendor's site but not the vendor `s7`;
  dated secondary `s4`, `s5`, `s6`; the agent `s3`; an anecdote `s8`. To pick the next, run
  `served.mjs cloud-hosting-2026-10 c-check-vendor-claims`, take a source not yet served, and
  prefer a kind the learner hasn't met. Serve a near-miss (`s2`, `s7` or `s9`) before `s1`, so the
  learner meets a vendor page that doesn't settle it before one that does. Stop when done when has
  been met on two or three sittings with different kinds, and offer `a-check-lab-answer`; using up
  the ten is not the target.
- **worked example:** judge a source not in the ten aloud: a blog post found by searching the
  claim. Say whose page it is (not the vendor's), whether it is dated, and whether it is about
  this claim; conclude it can tell you what to look for but not settle it; then name where to go
  instead, Render's own free-plan docs. At the first level of help on a real attempt, ask only
  "whose page is this?"
- **doesn't show:** the criterion asks the learner to find the settling sentence on the vendor's
  own pages. Judging a source they were handed shows they know which sources could settle a claim,
  but except for `s1` and `s10` not that they would find the right page themselves. The ten are
  fixed, so a later visit repeats one they have seen.
- **offer as:** the quickest route, about 10 minutes, mostly without a browser: one source at a
  time, judged on whether it could settle a claim at all, rather than how to find one. The only
  candidate whose bank is near-misses (a forum on the vendor's own site, a careful dated
  comparison with affiliate links, the vendor's docs about something else). Pick
  `a-check-2025-guide-claims` to do the finding yourself.
- **check note:** Don't let a run of non-settling verdicts suggest that nothing could settle the
  claim: say once that Render's free-plan docs, https://render.com/docs/free, would. On `s4`, orientation had the
  learner skim only the first line of each vendor in Odin's lesson, so they probably haven't seen
  that its Render paragraph says both "$7" and "expires 30 days". If they judge it without opening
  it, tell them the paragraph says both, then ask "when was this true?"

### `a-check-lab-answer`

- **serves:** `c-check-vendor-claims`
- **supports:** attempt
- **checks:** `c-check-vendor-claims`
- **artifact:** no external source. One claim about a vendor's free tier from an agent's answer to
  the learner's table's session 11 lab prompt, kept word for word. By default the answer is a
  fresh rerun of the table's prompt, or a tablemate's answer, and the claim is about a vendor the
  learner has not yet visited or signed up for. 10 to 15 minutes, with a browser.
- **learner does:** reads the one claim the tutor picks from the answer, then checks it live, alone:
  finds on the vendor's own current pages the sentence that settles it (opening a link the agent
  gave to the vendor's page counts), copies it with its address, and says whether the claim still
  holds.
- **tutor role:** none
- **tutor does:** picks one claim from the answer about free tiers, limits or cards, on a vendor
  the learner hasn't visited, and before the attempt checks it on the vendor's own pages that day,
  writing the key: the settling sentence, its address, and whether the claim holds. Waits,
  writing down any help word for word. Sends the adjudicator the claim, the key, the learner's
  sentence, address and verdict, and the help. Labels the attempt
  `a-check-lab-answer/<vendor>`.
- **done when:** criterion met with no help, on this one claim.
- **generator:** the material is whatever the learner's agent said in the lab, so no two
  instances match and nobody sets the difficulty. Hold fixed: one claim per attempt, about a
  vendor's free tier, limits or card, on a vendor the learner hasn't already visited; the key comes
  from the vendor's own pages on the day. If the answer holds no such claim, the tutor uses a
  rerun of the table's prompt or a tablemate's answer instead. Prefer a claim that turns out
  stale, when the answer has one. On review visits, use a fresh claim, from a fresh answer if
  need be.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "where would the vendor itself say that?", and the attempt is recorded `unaided: no`.
- **doesn't show:** the tutor picks the claim, so a pass doesn't show the learner would pick out
  the claims worth checking in a whole answer. Whether the claim turned out stale is luck. The key
  rests on the tutor's reading of the vendor's pages on one day.
- **offer as:** the real thing: a claim from your own table's prompt, on a vendor you haven't
  looked at yet, checked on the vendor's own pages. Any time after the session 11 lab.

### `a-weigh-described-plans`

- **serves:** `c-weigh-hosting-plans`
- **supports:** attempt
- **checks:** `c-weigh-hosting-plans`
- **artifact:** no external source. An app, two plans and made-up vendors' free-tier terms, with
  one question at a time on one case of weighing them. 5 to 10 minutes a question.
- **learner does:** reads the app, the plans and the terms, then answers the one question alone.
  Each question carries one case: what each plan's free terms mean (sleep, limits, card); whether
  their agent can reach each host; what the extra vendor adds and how hard each plan is to move; or
  choosing a plan and making the strongest case for the other. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** serves the question and its key; when the generator is run live, writes the key
  into the record before showing anything. Shows the app, the plans, the terms and the one
  question. Waits, writing down any help word for word. Sends the adjudicator the question, the key,
  the learner's answer verbatim and every piece of help, naming the one case the question carries, with the reminder that which plan anyone chose is never judged. After the ruling, tells the
  learner what was missed or unsupported. Labels the attempt with the question's path, or
  `a-weigh-described-plans/<case>-<twist>` when the generator is run live. A remark about where the
  database goes is neither credited nor counted as a false gap or an unsupported claim: the tutor
  tells the adjudicator to disregard it, and the learner that it belongs to database-hosting.
- **done when:** the criterion, as it applies to the question's one case, met with no help; the
  case is recorded with `--cases`.
- **generator:** fixed: the app is a class project with a React frontend and an Express server,
  used by about twenty people, built by someone working through a coding agent; its database is
  never part of the plans, the terms or the key. In what the learner sees, state the task, never the scoring: no criterion guard such as "and
  nothing that isn't one" or "name nothing the terms don't support". A setup may say what the plans
  or terms contain and that something, like the database, is outside them; it never tells the
  learner how they will be scored, and a remark about the database is the tutor's and the rubric's
  matter. Plan one puts the frontend and backend with one
  vendor; plan two uses a separate vendor for each. Vendors are made up. Each vendor's terms are
  four to six bullets, always covering: whether anything sleeps and how long it takes to wake; what
  happens past each limit (paused, suspended, stopped when credit runs out, billed with a card);
  whether a card is required, and what a card on file allows the vendor to bill; agent access
  (whether there is an official command-line tool, an MCP server or an API, and what it can and
  can't do: deploy, set environment variables, read logs); and moving (standard tools and exports,
  or something vendor-specific). Every question bears on `c-weigh-hosting-plans` and **carries
  exactly one case**, named on its rubric `cases:` line: `free-limits` (sleep, limits and card, for
  both plans), `agent-reach` (each host's reach and what the agent can't do there),
  `vendor-count` (what the extra vendor adds, and how hard each plan is to move) or `other-case`
  (choose, and the strongest case for the other plan). A question may ask the case directly or through a student's
  answer to judge. A scenario covers all four cases across its questions, and no question's text
  gives away a later question's answer. What varies: the terms, and the twist, each tied to the
  case it carries:
  - `lopsided` (Easy, `other-case`): one plan is better on most of the terms, and the
    strongest case for the other is still real.
  - `balanced` (Medium, `other-case`): each plan wins on at least two kinds of term.
  - `agent-gap` (Medium, `agent-reach`): the single vendor's agent tool can't read the
    backend's logs, or one split vendor has no command-line tool or MCP server at all, only a
    dashboard.
  - `card-trap` (Hard, `free-limits`): every vendor signs up without a card, but one bills
    overages once a card is added (for example, after the learner adds one to unlock a feature);
    or one asks for a card only to verify identity and can't bill it. A pass has to tell these
    apart.
  - `hard-move` (Medium, `vendor-count`): one vendor builds with its own config or
    exports only in its own format, so moving off it is real work.
  - `irrelevant-difference` (Hard, `other-case`): one large difference that doesn't matter
    for twenty users (a bandwidth allowance of 100 GB against 1 TB, a region list, team seats); a
    case resting on it doesn't rest on a difference that matters.
  A new scenario always invents new vendor names, never one on the topic's list of names in use
  (at the head of this file).
  Difficulty as marked. Across visits, serve each case, and `agent-gap` and `card-trap` at least
  once each, reading the labels `served.mjs` returns.
- **worked example:** work one Easy question aloud on the same case as the one being asked: for
  free limits, go through sleep, limits and card for each plan in turn; for agent reach, host by
  host, what the tool can and can't do; for vendor count, what each extra account brings and what
  moving off each vendor takes; for the other case, pick a plan, then argue the other one from the
  difference that matters most for twenty users. For what a card on file can risk, tell, as
  history, the ServerlessHorrors story "$104,500", https://serverlesshorrors.com/all/netlify-104k/
  (February 2024): a DDoS on a static site on Netlify's free plan ran up a $104,500 bill, later
  waived; Netlify's free plan now has a hard limit with no overage. At the first level of help on a
  real attempt, ask only the case's first question (for free limits, "what happens on each plan
  when nobody has visited for an hour?").
- **doesn't show:** one question carries one case, so a pass shows that case only; the goal is met
  only when all four cases have passed. The terms are stated plainly in a few
  bullets each, so a pass doesn't show the learner could find them on real vendors' pages, where
  they are spread over pricing, docs and billing pages and agent access is on a page of its own.
  Vendors are made up, so a pass says nothing about real ones. The two plans are always one vendor
  against a vendor for each part, and the database is left out. The learner knows a check is on.
- **offer as:** the check that's available now: two plans the tutor wrote, one case at a time, 5
  to 10 minutes a question, nothing to run, and the tutor picks the twist so the hard cases (a card that can be billed once
  added, an agent that can't see the backend's logs) actually come up. `a-weigh-lab-plans` is the same
  capability on two plans from your own lab.

### `a-weigh-lab-plans`

- **serves:** `c-weigh-hosting-plans`
- **supports:** attempt
- **checks:** `c-weigh-hosting-plans`
- **artifact:** no external source. Two plans for the learner's own Problem Set 2 app taken from the
  session 11 lab (their agent's answer and a tablemate's, or one answer's two options), one putting
  the frontend and backend with a single vendor and one using a separate vendor for each, with the
  vendors' free-tier terms as the tutor gathers them from the vendors' own pages. The database is
  left out. One case per sitting, 10 minutes, plus the tutor's preparation.
- **learner does:** reads the two plans and the terms sheet, then answers alone the one question
  the tutor sets, on one case, as in `a-weigh-described-plans`: what each plan's free terms mean;
  whether their agent can reach each host; what the extra vendor adds and how hard each plan is to
  move; or which plan they would choose for Problem Set 3 and the strongest case for the other.
  Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, picks two plans from the lab that fit the criterion's shape;
  if none does, builds the second from the first (the single vendor's own two services, or a
  separate vendor for each part from the vendors the lab answers named). For each vendor, reads its own current
  pages and writes a terms sheet in the bullets of `a-weigh-described-plans`'s generator, with the
  address and date of each page; the sheet must include agent access, from the vendor's own docs
  on its command-line tool, MCP server or API (for example, on 2026-10-01: Render's MCP server,
  https://render.com/docs/mcp-server, which can create services, set environment variables, read
  logs, but cannot delete resources or change most settings; Netlify's MCP server and CLI,
  https://docs.netlify.com/build/build-with-ai/netlify-mcp-server/). If a lab answer proposes
  Hatchable, notes that its runtime "is a sandbox, not Node" with "No `npm install`"
  (https://hatchable.com/docs/developers/restrictions, checked 2026-10-01), so an Express backend
  would have to be rewritten: a port, not a deploy, and deep lock-in. Where a vendor's pages don't
  settle a term, writes "not stated by the vendor" rather than guessing. Leaves database terms out
  of the sheet and the key. Picks the one case for this sitting, preferring one not yet passed, and
  writes that case's key as in `a-weigh-described-plans`. Waits during
  the attempt, writing down help word for word. Sends the adjudicator the plans, the sheet, the
  key, the answer and the help, naming the one case. Labels the attempt
  `a-weigh-lab-plans/<case>-<single vendor>-vs-<split vendors, joined with +>`. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** the criterion, as it applies to the sitting's one case, met with no help; the case
  is recorded with `--cases`.
- **generator:** the material is whatever the lab produced, so nobody sets the difficulty. Hold
  fixed: one single-vendor plan and one plan with a separate vendor for the frontend and the backend; terms from the vendors' own
  pages on the day, never from an agent's answer; every sheet covers sleep, limits, card, agent
  access and moving, or says the vendor doesn't state it. Each sitting asks one question on one
  case (`free-limits`, `agent-reach`, `vendor-count` or `other-case`), recorded with `--cases`, and
  the same sheet serves all four across sittings. On review visits, use
  different vendors, or the same vendors with terms re-read that day, since they may have changed.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  the case's first question (for free limits, "what happens on each plan when nobody has visited
  for an hour?"), and the attempt is recorded `unaided: no`.
- **doesn't show:** the tutor gathers the terms, so a pass doesn't show the learner could pull them
  from vendor pages themselves; `c-check-vendor-claims` covers finding out, and this covers
  weighing. One sitting shows one case. Which twists come up is luck: real terms may have no card
  trap or agent gap. The key
  rests on the tutor's reading of vendor pages on one day.
- **offer as:** the real decision you face in Problem Set 3, on the vendors your own lab turned up,
  with their real terms gathered that day. Best after the lab and before you sign up for the
  plan you'll use. `a-weigh-described-plans` is the one to take before the lab.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
