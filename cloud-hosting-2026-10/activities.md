# Activities: cloud hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-01. In both checks for placing parts and both checks for weighing plans, the tutor writes
the vendors' offers and terms, already distilled, for the learner. In the checks for vendor claims,
the learner only plans. So nowhere in this topic is the learner examined on reading a real vendor's
pricing, docs and billing pages unaided. Each entry's `doesn't show` admits its own part of this.
Taken together, it is the topic's one shared blind spot.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-place-app-parts` | say which kind of host the frontend and the backend each need, and whether a hosting plan covers them | Given an app with a React frontend and an Express backend, and a hosting plan listing each vendor and what it offers, says which part each vendor would host, and names any part the plan leaves without a host or puts on a host that cannot run it, or says both are covered. It passes when every gap and mismatch is found and nothing is named that isn't one, including for a plan where one vendor hosts both, or where the backend serves the built frontend itself. Where the database is kept is not part of it. |
| `c-check-vendor-claims` | find out whether what an agent says about a hosting vendor is true today | Given an agent's answer comparing hosting vendors, says how they would find out which of its claims about free tiers, limits and credit cards still hold. It passes when what they describe checks each claim against the vendor's own current pages, not against the agent, a blog post or a forum; would catch a free tier the vendor has since withdrawn, a limit that has changed, and a credit card requirement the answer left out; and says what they would add to the prompt so that every claim in the next answer comes with what they need to check it. Asking the agent whether it is sure does not meet it. |
| `c-weigh-hosting-plans` | choose between hosting plans for an app, knowing what each would cost | Given two hosting plans for the same app, one putting the frontend and backend with a single vendor and one using a separate vendor for each, along with each vendor's free-tier terms, chooses one and says why. It passes when they name each difference in the terms that would matter for a class project with few users (whether the app sleeps, what happens when it passes a limit, whether a credit card is required and what having one on file risks, whether their agent can reach the host to change its settings and read its logs, and how hard it would be to move); say what the extra vendors add in accounts, secrets and places to look when something breaks; name nothing the terms don't support; and state the strongest case for the plan they didn't choose. Which plan they choose is not part of it, and neither is where the database is kept. |

## Coverage

<!--
  Derivation convention: an activity carrying `checks` sits only in the `checks` cell, never in
  `study`. Activities whose `serves` is `all` sit on the `o-orientation` row only.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-read-odin-deployment` | `a-dry-run-hosting-asks` | |
| `c-place-app-parts` | `a-read-fso-serve-dist`, `a-judge-plan-coverage` | `a-place-described-plan`, `a-place-lab-plan` | The criterion's two named cases overlap: a backend that sends the built frontend is also one vendor hosting both, through a single service. Read the Coverage note's two cases as two instance shapes, one vendor with two services and one service sending both parts. A counting pass usually exercises one shape; if the learner's pass came on one, give the other in study or on a review visit. |
| `c-check-vendor-claims` | `a-watch-claims-checked`, `a-check-2025-guide-claims`, `a-sort-claim-sources` | `a-plan-claim-checks`, `a-check-lab-answer` | Both checks rule on a written plan for checking claims, not on checks actually carried out. `a-check-lab-answer` has the learner carry the plan out, but the ruling is on the plan as first written. No check here establishes that the learner can find the settling sentence on a real vendor's site unaided, although the topic's Depth says they should be able to check a claim against the vendor's own pages. If that matters for this learner, look at what they found in `a-check-lab-answer`, or watch them do it in `a-check-2025-guide-claims`, and treat it as evidence beside the ruling, not as part of it. |
| `c-weigh-hosting-plans` | `a-study-hatchable-traps`, `a-predict-overage-outcomes`, `a-judge-plan-weighings` | `a-weigh-described-plans`, `a-weigh-lab-plans` | |

---

## Activities

### `a-read-odin-deployment`

- **serves:** `all`
- **supports:** orient
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
  Says secrets, backups and debugging are later topics. Makes no change to the learner's app.
- **done when:** both stops have an answer tied to the learner's own app: a sketch with the
  frontend and backend boxes labeled and the database box marked "see database-hosting", and one
  vendor placed against a box with one thing to check.
  No `checks`: the readiness indication `o-orientation` is ruled on is taken in
  `a-dry-run-hosting-asks`, which follows.
- **offer as:** this topic's orientation, deliberately one entry holding a sequence: two sections
  of a short MDN page that supply the static web server, then the first half of Odin's lesson,
  which supplies hosting providers, PaaS, instances and four real vendors, skimmed. About 15
  minutes with the stops; with `a-dry-run-hosting-asks`, about 20. Odin's vendor numbers are a year
  or so behind in places, and the tutor flags them if they come up; that is part of the lesson,
  not a defect in the choice. Followed by `a-dry-run-hosting-asks`.
- **check note:** At stop 1, a frontend labeled "sent by the Express server itself" passes the check
  as well as one on a host that sends files: some Problem Set 2 apps already serve `dist/` from
  Express, and that arrangement is covered under `c-place-app-parts`. Don't steer the learner off
  it.

### `a-dry-run-hosting-asks`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** no external source. The learner's three-box sketch and their answers from
  `a-read-odin-deployment`, still in front of them. About 5 minutes. Nothing needs to be running.
- **verified:** 2026-10-01
- **learner does:** two quick rehearsals, neither judged, each answered in a sentence. First, the
  tutor describes a made-up app's frontend and backend and one vendor's offer in a line, and the learner
  says which part that vendor could host, or none. Second, the tutor gives one line of terms from
  each of two plans, and the learner says one difference between them that would matter for a
  class project. (Finding out whether a vendor claim is true was rehearsed at the reading's second
  stop.) Then answers the question the tutor puts: with your sketch and the reading beside you,
  could you now attempt these three things for real: saying which kind of host an app's frontend
  and backend each need and whether a plan covers them; finding out whether what an agent says about a
  hosting vendor is true today; and choosing between two hosting plans knowing what each would
  cost you?
- **tutor role:** explainer
- **tutor does:** sets the two rehearsals from the generator below and grades neither. If an
  answer shows a misunderstanding (the frontend needing a server host because it is React; "free"
  as the only difference worth naming),
  explains it once and moves on. Then puts the readiness question as written above and rules on
  the answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's own indication, not on the rehearsals and not on
  whether the tutor thinks they are ready. A plain yes to all three parts is `criterion: met`. A
  hedge on any part, with no plain no, is `criterion: unclear`: explain the hedged part once more
  and put the question again; a second hedge stays `unclear`, and the tutor offers a study activity
  on that capability. A plain no to any part is `criterion: not met`: record it, ask what is
  missing, and offer to go back over the reading's stops that bear on the capability named, or a
  study activity on it; don't put the question again in the same sitting. This goal isn't
  required, so a no never blocks anything else the learner wants to try.
- **kind:** generator
- **generator:** vary the made-up app and the two items; hold the rest fixed. The app is small,
  with a React frontend and an Express server, used by a class (a study-group finder,
  a club sign-up sheet, a recipe box, a used-textbook board). Rehearsal one is one plan line from
  `a-place-described-plan`'s generator at Easy: one vendor, one offer, one part. Rehearsal two is
  one dimension from `a-weigh-described-plans`'s generator (sleep, past a limit, card, agent
  access, or moving), one line per plan, at Easy. Fixed: two rehearsals in that order, neither
  graded, then the readiness question word for word. Difficulty doesn't vary: this settles an
  indication, not a capability.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about any of the three capabilities: every rehearsal is helped, ungraded and of the
  easiest kind, a one-sentence answer never has to be complete, and claim checking is rehearsed
  only at the reading's second stop. It shows nothing about the
  fifteen words, which have their own supply.
- **offer as:** the short step that closes orientation, after `a-read-odin-deployment`. Not an
  alternative to it: the reading gives you the shape, and this is where you say whether you have
  it. About 5 minutes, nothing to run; about 20 with the reading.

### `a-read-fso-serve-dist`

- **serves:** `c-place-app-parts`
- **supports:** deepen
- **artifact:** Full Stack Open, part 3b, "Deploying app to internet",
  https://fullstackopen.com/en/part3/deploying_app_to_internet (University of Helsinki; free, no
  account; checked 2026-10-01). Two sections only: Serving static files from the backend, and The
  whole app to the internet. The sections contain commands and
  short code; the one line that matters is `app.use(express.static('dist'))`, which makes the
  Express server send the frontend's built files itself, so frontend and backend are at the same
  address. Skip everything about Fly.io and Render setup (that is how to deploy, past this topic's
  depth, and its vendor details may lag like Odin's), Frontend production build, Same origin
  policy and CORS, and Proxy. 10 to 15 minutes.
- **verified:** 2026-10-04
- **learner does:** reads the two sections without running anything. Then draws one arrangement of
  their own Problem Set 2 app: the Express server sending the built frontend itself, labeled with
  the kind of host it needs (the database is left out; it belongs to the database-hosting topic).
  Then answers: what does this plan no longer need? If a classmate's plan used this arrangement
  and named no static host, would that be a gap?
- **tutor role:** socratic questioner
- **tutor does:** stays out of the reading unless asked; if the learner stalls on the code, says
  only that `npm run build` makes a folder of plain files and `express.static('dist')` tells the
  server to send them. On the drawing, asks a near-miss question ("the frontend has no host of its
  own; is it unhosted?").
- **done when:** the drawing labels the server with the kind of host it needs, and the learner
  says that a missing static host in this arrangement is not a gap. No `checks`: the arrangement was shown to
  them, and their own app is one they already know.
- **offer as:** the one candidate about the arrangement the criterion singles out, the backend
  serving the built frontend itself, shown in the course material many full-stack courses use.
  Some code on the page, though the learner runs none. 10 to 15 minutes. Pick
  `a-judge-plan-coverage` to judge one plan at a time instead.

### `a-judge-plan-coverage`

- **serves:** `c-place-app-parts`
- **supports:** deepen
- **artifact:** `tasks/judge-plan-coverage.md`, written for this topic, used as a bank of eleven
  plans, one per sitting. Its header (about 370 words) describes Crumbs, a React and Express app
  shaped like the learner's Problem Set 2 app, whose plans place only the frontend and the backend
  (its database belongs to the database-hosting topic), and four made-up vendors, each saying in
  a line what it offers (a files-only host, a host that runs a program, a host that runs short
  functions and keeps nothing running, and one offering both static sites and web services).
  Each plan is one to three lines and reads alone. The key, one row per plan with its case, is in
  `tasks/judge-plan-coverage-key.md`, for the tutor only. Cases: clean split `q1`; one vendor
  hosts both `q5`; backend serves the frontend `q3`, `q10` (also hosted twice); decoy `q8`
  (functions host used only for files); gap `q6` (frontend), `q11` (backend left on a laptop);
  mismatch `q2` (Express on a files-only host), `q4` (Express on a functions host), `q12` (inside
  one vendor hosting both), `q13` (the backend serving the frontend from a host that can't run
  it). 10 to 15 minutes a sitting. Nothing to run.
- **kind:** bank
- **bank:** the eleven plans in `tasks/judge-plan-coverage.md`, named `q1` to `q6`, `q8` and
  `q10` to `q13`. To pick the next,
  run `served.mjs cloud-hosting-2026-10 c-place-app-parts`, take a plan not yet served, and prefer a case the
  learner hasn't met, from the list above; a good first three are `q3`, `q4` and `q6`, which
  carry the cases students most often miss. Label the attempt `a-judge-plan-coverage/<plan>`, for
  example `a-judge-plan-coverage/q4`. Stop when done when has been met on two or three sittings
  with different cases, and offer `a-place-described-plan`; using up the bank is not the target.
- **verified:** 2026-10-04
- **learner does:** reads the header and the one plan served, then says which part each vendor in
  it hosts and names every gap and mismatch, or says both are covered. Then says in a
  sentence the rule they judged by.
- **tutor role:** critic
- **tutor does:** shows the header and the one plan, never the key file. Takes the learner's answer
  and rule before commenting. Where the answer disagrees with the key, asks what that vendor would
  actually do with the part it was given ("Brightpage gets the Express server; what does it do
  when a request for recipes arrives?") rather than giving the verdict. If this plan's partner in
  the key has been served before, asks how this plan differs from that one and whether the answer
  should differ too (for `q6` after `q3`, "last time the frontend had no host of its own and was
  fine; what is different here?"; for `q12` after `q5`, "last time Harbor hosted both and that
  was fine; what is different here?"). If the answer still differs from the key after that one
  question, gives the key's verdict and its what-decides-it line, and moves on. If the learner
  raises where the database goes, says that belongs to the database-hosting topic.
- **done when:** the learner's answer on this plan matches the key, every gap and mismatch and
  nothing else, after at most one near-miss question; and their stated rule covers what each part
  needs and checking each vendor's offer against the part it was given. No `checks`: every plan in
  the bank uses the same four vendors, and each sitting ends with the key's verdict discussed, so
  from the second sitting on the learner is judging vendors whose fit they have already been
  told. A pass shows nothing about meeting new offers cold, which is what
  `a-place-described-plan` sets.
- **offer as:** one plan for one familiar-shaped app, 10 to 15 minutes, nothing to run, with the
  near-misses careful students most often get wrong (calling a backend-served frontend unhosted,
  flagging a vendor for a job it wasn't given) spread across the bank. Made-up vendors, so nothing
  here goes stale. Take a few across visits.

### `a-place-described-plan`

- **serves:** `c-place-app-parts`
- **supports:** attempt
- **checks:** `c-place-app-parts`
- **artifact:** no external source. A made-up app and hosting plan, written by the tutor per the
  generator below. 10 minutes.
- **verified:** 2026-10-01
- **learner does:** reads the app's parts and the plan, then writes alone, for each vendor, which
  part it would host, and then names every part left without a host or put on a host that cannot
  run it, or says both are covered. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and writes the key into the record before
  showing anything: which part each vendor hosts, and every gap and mismatch, or "both
  covered". Shows the app's parts and the plan. Waits, writing down any help word for word. Sends
  the adjudicator the parts, the plan, the key, the learner's answer verbatim and every piece of
  help. After the ruling, tells the learner what was missed or named wrongly. Labels the attempt
  `a-place-described-plan/<shape>`. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** criterion met with no help, on a `backend-serves`, `shared-vendor`, `decoy` or
  `two-faults` instance.
- **kind:** generator
- **generator:** fixed: the app has a frontend and a backend, described in a short list in the
  form of `tasks/judge-plan-coverage.md` (what each part is and what it needs to run); the app's
  database is never part of the plan or the key. The plan names one to three vendors, each with a
  one- or two-line offer written as that file writes them: what it hosts and runs, and what it does
  not. Vendors are made up, so the key depends only on the stated offers. Brightpage, Kettle,
  Spark and Harbor may be used for the worked example and for practice; a counting
  instance invents new vendor names on the same pattern and never reproduces any plan in
  `tasks/judge-plan-coverage.md`, which the learner may have judged with its key discussed. What
  varies: the app (a different one each attempt; its frontend is React or another framework built
  to static files, its backend Express or another long-running server), the vendors and their
  offers, and the plan's shape:
  - `split-clean` (Easy): one vendor per part, both covered.
  - `one-gap` (Easy): one part left without a host.
  - `wrong-host` (Medium): one part on a host that cannot run it as the app is now (a long-running
    server on a files-only or functions-only host).
  - `backend-serves` (Medium): the backend sends the built frontend itself and no static host is
    named; both covered, or the backend on a host that cannot run it, in which case the key names
    the backend mismatch and says the frontend is then not served either, and the answer must say
    both.
  - `shared-vendor` (Medium): one vendor hosts both parts as separate services; both covered, or
    with one mismatch inside that vendor.
  - `decoy` (Hard): both covered, but the backend sends the built frontend itself and the frontend
    is also put on a static host, or a vendor hosting both has a limitation that doesn't bear on
    either part it was given (never a limitation about databases); either way it invites a false
    gap or mismatch.
  - `two-faults` (Hard): both parts faulted, one a gap and one a mismatch, with the mismatch on a
    vendor that offers both kinds of hosting (for example, the Express server put in that vendor's
    static-site service, and nothing named for the frontend).
  Difficulty as marked. **Only `backend-serves`, `shared-vendor`, `decoy` and `two-faults` count**,
  because each contains a case the criterion names (one vendor hosting both, or the backend
  serving the built frontend) and the bar is one unaided pass. `split-clean` and `one-gap`
  (Easy) are for the worked example and for a retry with help after a miss; `wrong-host` (Medium)
  is practice only, since its plan contains neither named case. For review visits, serve a
  counting shape the learner hasn't had, reading the labels `served.mjs` returns.
- **worked example:** work one Easy instance aloud: list what each part needs, then go vendor by
  vendor saying what it was given and whether its offer can do that job, and finish by checking
  each part has somewhere to live. At the first level of help on a real attempt, ask only "what
  does each part need from a host?"
- **doesn't show:** the offers are stated plainly in a line each, so a pass doesn't show the
  learner could work out what a real vendor offers from its own pages, where the answer is spread
  over pricing and docs. Vendors are made up, so a pass says nothing about knowing which real
  vendor does what. Where the database is kept is left out, as the criterion says. The learner
  knows a check is on.
- **offer as:** the check that's available now: a made-up app and plan, 10 minutes, nothing to
  run, and the tutor picks the shape so the two cases the criterion names (one vendor hosting
  both, the backend serving the frontend) actually come up. `a-place-lab-plan` is the
  same capability on the plan your own lab prompt produced.
- **check note:** A `decoy` instance is always fully covered, and a `backend-serves` or
  `shared-vendor` instance may be. A pass on one of those shows the learner did not name a false
  gap, not that they can find a real one. For the counting attempt, prefer an instance that contains
  at least one gap or mismatch. If a learner's only pass came on a fully covered plan, tell them so
  and offer a faulted instance on a later visit.

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
  names every gap and mismatch, or says both are covered. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, reads the learner's app (the learner need not see this) to
  list its parts as they are now: what the frontend builds to, whether the backend already sends
  the built frontend. The database is left out of the plan, the offers and the key; it belongs to
  the database-hosting topic. Turns the answer into a plan for the frontend and backend: if it already says which vendor hosts which part, uses that; if it is a
  comparison, takes the vendors it recommends and assigns each to the part the answer suggests it
  for; if the answer suggests nothing for some part, assigns one of the vendors it names to that
  part the way a student reading the answer plausibly would, and records that the tutor did this.
  For each vendor in the plan, reads that vendor's own current pages and writes its offer in a
  line or two, as `tasks/judge-plan-coverage.md` writes them, with the address and date of each
  page used, written from those pages that day; the offer must not be the agent's description of
  it, and a real functions host whose pages now say it runs an Express server unchanged is not a
  mismatch. If a vendor's pages don't settle
  whether it can run the part it was given, replaces it with another vendor the answer names whose
  pages do; if there is none, shows that part's line as "not judged: the vendor's own pages don't
  settle this", tells the learner to leave that part out, and leaves it out of the key, so the
  missing offer is never mistaken for a planted gap. Writes the key into the record from the
  offers. **Counts the instance only if the plan has one vendor hosting both or a backend serving
  the built frontend.** Any other plan, faulted or not, is practice only; the tutor says so and offers
  `a-place-described-plan` for the counting attempt. Waits during the attempt, writing down any help word for word. Sends the
  adjudicator the parts, the plan with its offers, the key, the learner's answer and every piece
  of help. Labels the attempt `a-place-lab-plan/<vendors, joined with +>`. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is whatever the learner's agent proposed, so no two instances match
  and nobody sets the difficulty. Hold fixed: offers come from the vendor's own pages on the day,
  never from the agent's answer; the key comes from those offers and the app's code. Only a plan
  with one vendor hosting both or a backend-served frontend counts, for the reason above. Across visits, use a different agent answer each time (a tablemate's, or a fresh run of
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

### `a-watch-claims-checked`

- **serves:** `c-check-vendor-claims`
- **supports:** orient, deepen
- **artifact:** Hatchable, "Free web hosting in 2026",
  https://hatchable.com/articles/state-of-free-web-hosting-in-2026 (updated 2026-08-21, no author
  named; written by a hosting vendor; checked 2026-10-01), used as a source of dated claims, plus
  the vendors' own pages opened live. A bank of four claims from the article, one per sitting:
  in each, the tutor makes the first lookup aloud, false start included, and the learner finishes
  the check. 10 to 15 minutes a sitting. Cases: `c1` holds, with a consequence to find; `c2`
  holds for one vendor and the vendor's pages don't settle it for the other; `c3` an omission
  whose answer is split across two of the vendor's pages; `c4` stale.
  - `c1`: "Render's free Postgres, for instance, expires 30 days after creation per its changelog, with
    a grace period to upgrade before deletion." (Render's own page on 2026-10-01:
    https://render.com/docs/free, 30 days and a 14-day grace period, after which Render "deletes
    the database (along with all of its data)".) Tutor's half: searches the claim, lands on a
    blog post, says why that doesn't settle it. Learner's half: finds Render's own sentence, and
    what happens after the grace period. **Status: holds.**
  - `c2`: on Neon and Supabase: "both have free tiers with a small database (hundreds of megabytes),
    compute that sleeps or pauses when idle, and no card". (Neon's pricing page,
    https://neon.com/pricing, says "no credit card required", and on 2026-10-02 storage of "1 GB/project",
    so "hundreds of megabytes" is now stale for Neon; Supabase's pricing page,
    https://supabase.com/pricing, says "500 MB database size" and "Free projects are paused after
    1 week of inactivity", so those hold, and it did not say either way about a card.) Tutor's
    half: Neon, on its pricing page. Learner's half: Supabase, where size and pausing are settled
    and only the card is not; for that, "I'd find out at sign-up" is the answer, not the article's
    word. **Status: mixed** (Neon's size stale; the rest holds, except Supabase's card, unsettled).
  - `c3`: "Fly.io no longer has a general free tier for new accounts, only a short trial before
    pay-as-you-go." This sentence says nothing about a card or about how short the trial is;
    the article's FAQ says elsewhere that "Fly.io wants one once its short trial ends". Fly's own
    pages split the answer across two places. Its free-trial page,
    https://docs.fly.io/about/free-trial/, says the trial "includes 2 hours of machine runtime or 7
    days of access, whichever comes first", needs no card to start, and that "adding a card ends
    the free trial"; when it expires without one, "your apps will stop running". Its pricing page,
    https://docs.fly.io/about/pricing/, says "All organizations (except for Linked Organizations)
    require a credit card on file". Tutor's half: opens the pricing page, reads the card
    sentence and nearly concludes a card is needed to sign up. Learner's half: the trial page,
    and the fuller answer (no card to start, 2 hours or 7 days, a card needed to keep going).
    **Status: omits** (true as far as it goes; leaves out the length and the card).
  - `c4`, from the article's The traps to watch for: "Railway's
  $5/month credit is a trial, not a free tier. When you exceed it, you pay." Railway's own docs,
  https://docs.railway.com/reference/pricing/free-trial, on 2026-10-01: the trial is "a one-time
  grant of $5" for "up to 30 days", after which the account "reverts to the Free plan", which
  "provides $1 of free credit per month" that "does not roll over". So the article's sentence is
  stale twice over: the $5 is one-time, not monthly, and there is a standing free plan after it.
  (Flavio Copes, "Every hosting provider's free tier, side by side",
  https://flaviocopes.com/hosting-free-tiers/, data checked 2026-09-16, with disclosed affiliate
  links, gives Railway's "$1 of credit a month, no rollover" correctly.) Tutor's half: opens
  Copes's table, finds that it contradicts the article, and says why a careful dated table still
  isn't the page that settles which one is right. Learner's half: Railway's own docs, and both
  ways the article's sentence is stale (one-time, not monthly; a free plan after it). **Status:
  stale.**
- **kind:** bank
- **bank:** the four claims above, named `c1` to `c4`. To pick the next, run
  `served.mjs cloud-hosting-2026-10 c-check-vendor-claims`, take a claim not yet served, and prefer
  a case the learner hasn't met; `c3` or `c4` makes a good first sitting. Label the attempt
  `a-watch-claims-checked/<claim>`, for example `a-watch-claims-checked/c3`. Once the learner has
  met Render's 30-day expiry anywhere in this topic, prefer claims about other vendors. Stop when
  done when has been met on two or three sittings with different cases, and offer
  `a-plan-claim-checks`; using up the bank is not the target.
- **verified:** 2026-10-02
- **learner does:** hears the claim and says where they would look before the tutor starts. Watches
  the tutor's half aloud in a browser and interrupts whenever they disagree or can't follow. Then
  does the learner's half themselves while the tutor watches, saying aloud where they are looking
  and why, and ends by saying whether the claim holds, is stale, or can't be settled from the
  vendor's pages, with the sentence that shows it. Last, one sentence they would add to a prompt
  so an agent's claim like this one comes with what they need to check it.
- **tutor role:** explainer
- **tutor does:** before the sitting, opens the vendor pages for this claim and confirms they still
  say what is quoted; if they don't, uses what they say now and tells the learner the claim
  changed between curation and today, which is the point. Does the tutor's half for this claim,
  making the false start on purpose and naming it as one. Then hands over, saying nothing more
  than "where would the vendor itself say that?" if the learner stalls. Says what kind of page
  settled it (a free-plan docs page, a pricing page, a trial page) and whether it carried a date.
  For `c3`, points out that the article's sentence left out both the trial's length and the card,
  though its FAQ mentions the card, so reading one sentence of a source is not reading the source.
  If another claim has been served before, asks how the place that settled this one differs from
  the place that settled that one. On the prompt sentence, asks whether an agent could follow it
  (a link to the vendor's own page per claim, and the date of its information, are both things it
  can give). From the second sitting in any of this goal's three banks on, the prompt sentence is
  not written fresh: the tutor asks "would last time's sentence have caught this claim?" and the
  learner revises it.
- **done when:** the learner has finished this claim on the vendor's own page and given the right
  status (the bold status and the parenthesis above), can say why the tutor's false start
  didn't settle it, and has written or revised a prompt sentence asking for the vendor's own page. No
  `checks`: the tutor did half the check, and chose where to start.
- **offer as:** watch it done first, one claim at a time: the tutor starts the check on a claim
  from a vendor-written article, with the false start left in, and hands you the rest. The only
  candidate where you see where a check goes wrong (a blog in place of the vendor, a card rule
  split across a vendor's pricing and trial pages). Needs a browser and a live session, 10 to 15
  minutes. `a-check-2025-guide-claims` is all yours from the start.
- **check note:** On `c2`, treat Supabase's card the way `g3` in `a-check-2025-guide-claims` does.
  If the learner finds a sentence elsewhere on Supabase's own site that settles it, that answer is
  better than "I'd find out at sign-up". Accept "I'd find out at sign-up" only if they looked beyond
  the pricing page first. Your half of each check is narrated, so the learner isn't watching over
  your shoulder. Give each address and the sentence you read as you go, so the learner can open the
  page and object between steps.

### `a-check-2025-guide-claims`

- **serves:** `c-check-vendor-claims`
- **supports:** deepen
- **artifact:** `tasks/check-2025-guide-claims.md`, written for this topic, used as a bank of six
  sentences quoted exactly from the deployment guide given to students in this course's 2025
  predecessor (SI 211), about PlanetScale, Neon, Supabase and Render, one per sitting, under a
  short header and a five-step procedure. The key, checked against those vendors' own pages
  on 2026-10-01, is in its own file, `tasks/check-2025-guide-claims-key.md`, for the tutor only.
  One claim names a free tier since withdrawn (PlanetScale's free MySQL, whose plan ended in 2024).
  The rest hold, with something left out: Render's Postgres "only free for the first month" was
  already the 30-day rule when written (Render's changelog dates it to May 2024) but hides that the
  database is deleted with its data after a 14-day grace period; the others leave out sleep,
  pausing, or the card. None is a limit that has changed since 2025; that case is in
  `a-watch-claims-checked` (Railway's trial) and in `a-plan-claim-checks`'s generator. The guide itself is in the instructor's files and is not available to students, which is
  why its sentences are quoted. 10 to 15 minutes a sitting, with a browser.
- **kind:** bank
- **bank:** the six claims in `tasks/check-2025-guide-claims.md`, named `g1` to `g6`. Cases:
  withdrawn `g1`; holds but hides the consequence `g5`; holds with sleep or limits left out `g3`,
  `g4` (and `g3`'s card question isn't settled on the pricing page); holds `g2`; too vague to
  check as it stands `g6`. To pick the next, run
  `served.mjs cloud-hosting-2026-10 c-check-vendor-claims`, take a claim not yet served, and prefer
  a case the learner hasn't met; `g1` and `g5` make the best first two. Label the attempt
  `a-check-2025-guide-claims/<claim>`, for example `a-check-2025-guide-claims/g1`. Once the
  learner has met Render's 30-day expiry anywhere in this topic, prefer claims about other vendors
  over `g5`. Stop when done when has been met on two or three sittings with different cases, and
  offer `a-plan-claim-checks`; using up the bank is not the target.
- **verified:** 2026-10-02
- **learner does:** reads the header and the one claim served, then follows the five steps on it:
  says which page on the vendor's own site they expect to settle it and why; finds it and copies
  the sentence that settles it with its address and any date; says whether the claim holds, has
  changed, or is gone; says what it leaves out that they would want before signing up; and says
  what kind of page settled it, or that the vendor's pages couldn't. Ends with one sentence they
  would add to a prompt so an agent's claim like this comes with what they'd need to check it.
- **tutor role:** critic
- **tutor does:** before the sitting, opens the address in the key for this claim and confirms it
  still says what is quoted; where it doesn't, the page wins and the tutor updates its own copy of
  the verdict. Shows the header and the one claim, never the key file. Takes the learner's five
  answers before commenting. If the verdict rests on something other than the vendor's page (a
  search result's snippet, a comparison article, the agent), asks where the vendor itself says
  that. On `g1`: an absence on a pricing page is evidence only once you're sure it's the page that
  would list the plan. On `g5`: "free for a month" and "deleted after a month unless you pay" are
  different risks. On `g6`, "holds" passes once the learner says what "a free account" must mean
  (permanent, no card, how big, whether it sleeps) and checks that on neon.com; "too vague" passes
  only if they then make it checkable that way and check it. On `g3`, a card answer found
  elsewhere on Supabase's own site beats "I'd find out at sign-up". If another claim has been
  served before, asks how the page that settled this one differs in kind from the one that settled
  that. From the second sitting on, the prompt sentence is revised, not written fresh: "would last
  time's sentence have caught this claim?"
- **done when:** the learner's verdict on this claim rests on a quoted sentence from the vendor's
  own page, or an honest "the vendor's pages don't settle this", and matches the key (for `g1`,
  gone; for `g5`, the deletion found; for `g6`, as above); and they have named the kind of page and
  written or revised a prompt sentence. No `checks`: the claim was chosen for them and set out with a procedure to follow, and
  the prompt sentence is asked for.
- **offer as:** real claims, from a real guide given to students in this course a year ago, which
  was right when it was written, one at a time. You do the checking from the start, on real
  vendor pages, 10 to 15 minutes. The most hands-on of the study routes, and the one that shows
  how fast this goes stale. Pick `a-watch-claims-checked` to see it done first.
- **check note:** `g2` and `g6` are both settled on Neon's pricing page. If `g2` has been served,
  `g6` is mostly about deciding what a vague claim would have to mean before it can be checked, so
  put the weight there. The key notes that Neon's storage went from 0.5 GB to 1 GB per project
  overnight on 2026-10-02. Neither claim states a figure, so neither is stale. The change is still
  worth mentioning as an example of how fast these limits move.

### `a-sort-claim-sources`

- **serves:** `c-check-vendor-claims`
- **supports:** deepen
- **artifact:** no external source beyond the pages named here, all checked as resolving on
  2026-10-01. One claim, which the tutor states every sitting: "Render's free web services sleep
  after 15 minutes and its free Postgres is free for good." A bank of nine sources, one judged per
  sitting, each with its verdict and the tutor's near-miss question:
  - `s1` Render's docs, "Deploy for Free", https://render.com/docs/free. **Settles it**: the sleep
    half holds; the Postgres half is false (expires 30 days after creation, deleted after a
    14-day grace period). Question: none; the learner opens it and checks both halves.
  - `s2` Render's pricing page, https://render.com/pricing. Vendor's own page that doesn't address
    the claim: no spin-down or Postgres-expiry wording. Question: "does the pricing page say what
    happens when the service is idle, or when the database is a month old?"
  - `s3` The coding agent's own answer, asked "are you sure?". The agent again. Question: the
    criterion's own line, that asking the agent whether it's sure does not count; "where would its
    answer have come from?"
  - `s4` The Odin Project's Deployment lesson (read in orientation), Render paragraph. Dated
    secondary source, and it contradicts itself on Render's databases. Question: "when was this
    true?"
  - `s5` Hatchable, "Free web hosting in 2026". A vendor's article about other vendors, dated
    August 2026. Question: "whose page is it, and what does it want you to choose?"
  - `s6` Flavio Copes, "Every hosting provider's free tier, side by side", data checked
    2026-09-16, with disclosed affiliate links. Careful, dated, secondary. Question: "when was
    this true, and who would know if it changed yesterday?"
  - `s7` A 2024 thread on Render's own community forum, which used to be at community.render.com.
    That address now redirects to https://render.com/docs/community, which says "The community
    forum was sunset on March 24, 2026" (the community moved to Discord). On the vendor's site but
    not the vendor speaking. Question: "it's on Render's site; is it Render saying it?"; afterwards,
    the tutor adds that the forum has since been shut and its threads are stranded at the date
    they were written.
  - `s8` A classmate who signed up for Render last week. Recent, first-hand, but about one account
    on one day, and not about a database's 30th day. Question: "what could they have seen in a
    week?"
  - `s9` Render's MCP server docs, https://render.com/docs/mcp-server. Vendor's own page about
    something else. Question: "it's Render's own page; is it about this claim?" (it isn't; it
    matters for whether an agent can reach the host, which belongs to weighing plans).
  10 minutes a sitting; 15 for `s1`, which needs a browser.
- **kind:** bank
- **bank:** the nine sources above, named `s1` to `s9`. Cases: settles it `s1`; vendor's own page
  not about this claim `s2`, `s9`; on the vendor's site but not the vendor `s7`; dated secondary
  `s4`, `s5`, `s6`; the agent `s3`; an anecdote `s8`. To pick the next, run
  `served.mjs cloud-hosting-2026-10 c-check-vendor-claims`, take a source not yet served, and prefer
  a case the learner hasn't met. Serve a near-miss (`s2`, `s7` or `s9`) before `s1`, so the learner
  meets a vendor page that doesn't settle it before one that does. Label the attempt
  `a-sort-claim-sources/<source>`, for example `a-sort-claim-sources/s7`. The claim is about
  Render, so if the learner has already met Render's 30-day expiry elsewhere in this topic, skip
  `s1`. Stop when done when has been met on two or three sittings with different cases, and offer
  `a-plan-claim-checks`; using up the bank is not the target.
- **verified:** 2026-10-02
- **learner does:** hears the claim and the one source, and without opening it says: does this
  source settle the claim today, help only with knowing what to look for, or not help with this
  claim, and why. If it doesn't settle it, says where they would go instead. For `s1`, opens it
  and checks both halves of the claim on it. Ends with one sentence they would add to a prompt so
  an agent's claim like this one comes with a source that would settle it.
- **tutor role:** socratic questioner
- **tutor does:** takes the learner's verdict and reason before commenting. Asks this source's
  near-miss question from the bank rather than giving a verdict. For `s1`, makes sure the learner
  finds that the free Postgres expires after 30 days, so the second half of the claim is false. If
  another source has been served before, asks how this one differs from that one, and whether the
  verdict should differ too (for `s2` after `s9`, "both are Render's own pages; why might one of
  them settle it and the other not?"). On the prompt sentence, asks whether it would make the
  agent link the vendor's own page rather than a comparison article; from the second sitting on,
  asks "would last time's sentence have caught this?" and the learner revises it.
- **done when:** the learner rules rightly on whether this source settles the claim today (only
  `s1` does), with a reason that names what makes it settle or not (whose page it is, whether it is
  current, whether it is about this claim). For `s2` and `s4` to `s9`, either non-settling verdict
  ("helps with what to look for" or "doesn't help") passes with the right reason; for `s3` only
  "doesn't help" passes, since re-asking the agent adds nothing; where it doesn't settle it, they named the vendor's own current docs as
  where to go instead; for `s1`, they found the 30-day expiry. No `checks`: the source and the
  claim were handed to them, and the criterion asks them to say where they would look on their own.
- **offer as:** the quickest route, about 10 minutes, mostly without a browser: one source at a
  time, judged on whether it could settle a claim at all, rather than how to find one. The only
  candidate whose bank is near-misses (a forum on the vendor's own site, a careful dated
  comparison with affiliate links, the vendor's docs about something else). Pick
  `a-check-2025-guide-claims` to do the finding yourself.
- **check note:** Whether `s1` gets skipped depends on the route the learner took. Orientation skims
  the vendor paragraphs and raises Render's 30-day Postgres expiry only if the learner stopped on
  it, so a learner fresh from orientation usually still gets `s1`. A learner who has met the expiry
  in `a-watch-claims-checked` (`c1`), `a-check-2025-guide-claims` (`g5`) or
  `a-predict-overage-outcomes` has `s1` skipped, and this route then judges only sources that don't
  settle the claim. That is fine, because the route teaches what a source can and can't settle. But
  don't let a run of non-settling verdicts suggest that nothing could settle the claim: say once
  that Render's free-plan docs, https://render.com/docs/free, would. On `s4`, orientation had the
  learner skim only the first line of each vendor in Odin's lesson, so they probably haven't seen
  that its Render paragraph says both "$7" and "expires 30 days". If they judge it without opening
  it, tell them the paragraph says both, then ask "when was this true?"

### `a-plan-claim-checks`

- **serves:** `c-check-vendor-claims`
- **supports:** attempt
- **checks:** `c-check-vendor-claims`
- **artifact:** no external source. An agent's answer comparing hosting vendors, written by the
  tutor per the generator below, in an agent's voice. 15 minutes.
- **verified:** 2026-10-01
- **learner does:** reads the answer, then writes alone, claim by claim, how they would find out
  whether each claim about free tiers, limits and credit cards still holds: where they would look
  and what they would look for. Then writes what they would add to the prompt so that every claim
  in the next answer comes with what they need to check it. Does not open a browser: it is a plan,
  judged as written. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and, before showing anything, writes into
  the record each claim, its true status today, the vendor page that settles it (opened that
  day) with its address, the kind of page it is (pricing page, free-plan docs, trial page, billing
  docs, changelog), and which claims are the three planted kinds. Shows only the agent's answer. Waits,
  writing down any help word for word. Sends the adjudicator the answer, the key (with each settling
  page's kind), the learner's plan verbatim and the help, and the generator's rule below on what
  "would catch" means. After the ruling, opens the settling pages with the learner and shows
  which claims were stale. Labels the attempt `a-plan-claim-checks/<vendors, joined with +>`.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed: the answer is 150 to 300 words in a coding agent's voice, confident, with
  no sources and no dates, answering a lab-style prompt ("compare free hosting for a React,
  Express and SQLite class project"). It names three to five real vendors and makes six to nine
  claims about free tiers, limits and credit cards. Every instance plants all three kinds the
  criterion names:
  - `withdrawn`: a free tier the vendor has since withdrawn, stated as current.
  - `changed`: a limit stated as it used to be.
  - `card-omitted`: a vendor recommended with no mention of a card requirement it has.
  The remaining claims are true today. The tutor chooses each planted claim from what it can
  confirm that day on the vendor's own page and records the address; examples confirmed on
  2026-10-01, to be re-confirmed before use: `withdrawn`, PlanetScale's free MySQL plan (no free
  plan on https://planetscale.com/pricing), Heroku's free dynos (ended 2022), or Fly.io's free
  allowance for new accounts; `changed`, Render's free Postgres described as costing $7 or as
  lasting indefinitely (https://render.com/docs/free: free, expires after 30 days), Railway
  described as "a $5 credit every month" (https://docs.railway.com/reference/pricing/free-trial:
  a one-time $5 trial, then $1 a month), or Neon's compute described as always on
  (https://neon.com/pricing: scales to zero after 5 minutes); `card-omitted`, Fly.io recommended
  for its trial with no mention that a card is needed to keep going: its pricing page,
  https://docs.fly.io/about/pricing/, says "All organizations ... require a credit card on
  file", and its trial page, https://docs.fly.io/about/free-trial/, says no card is needed to
  start, the trial is 2 hours of machine time or 7 days, and "adding a card ends the free trial"
  (settling page: both, a pricing page and a trial page). Never plant a claim the tutor cannot settle on the
  vendor's own page that day. What varies: the vendors, which claims are planted, and the
  disguise:
  - `plain` (Easy): planted claims stated flatly.
  - `hedged` (Medium): the answer adds "as of my last update" or "prices may change", which tempts
    a plan that only re-asks the agent.
  - `sourced-wrong` (Medium): the answer cites a comparison article or a forum for one planted
    claim, which tempts a plan that checks the citation rather than the vendor.
  - `mixed-true` (Hard): one true claim sits next to each planted one about the same vendor (a
    true sleep time beside a wrong database limit), so a plan that checks "Render" as a whole
    rather than each claim can miss one.
  Difficulty as marked. An attempt meant to count runs at Medium or Hard. Across visits, serve
  `sourced-wrong` and `mixed-true` at least once each, reading the labels `served.mjs` returns.
  The plan passes when, followed as written, it checks every claim on the vendor's own current
  pages, would catch all three planted claims, and includes a prompt addition that would make each
  claim come with what is needed to check it (for example, a link to the vendor's own page for
  each claim, and the date of the agent's information). A plan that would check only the claims
  that look doubtful misses `card-omitted`, since an omission doesn't look doubtful; the plan has
  to say how it would find what a vendor requires, not only test what was said. "Would catch" is
  judged against the settling page recorded in the key, not against "the vendor's site" in
  general: a plan catches a planted claim if the place it says it would look, followed as
  written, would reach that page or one of the same kind on that vendor's site, and it says what
  it would look for there. A plan that says only "check the vendor's pricing page" for everything
  catches a claim settled on a pricing page, but not one settled only in trial, billing or
  free-plan docs; for those it must say it would look past the pricing table (the docs on the
  free plan or trial, the billing docs, or what the vendor's sign-up asks for). Naming the exact
  page or address is never required.
- **worked example:** work one Easy instance aloud: for each claim, name the vendor page that
  would settle it and why that page, then ask "what has the answer not said about this vendor that
  I'd need before signing up?" At the first level of help on a real attempt, ask only "for this
  claim, who would know for sure today?"
- **doesn't show:** it is a plan, not a check carried out, so whether the learner can find the
  settling sentence on a real vendor site (often spread over pricing, docs and billing pages) is
  not examined. The planted claims are of the three kinds the criterion names and no others. The
  learner knows a check is on and that stale claims are in there, which a real answer doesn't
  announce.
- **offer as:** the check that's available now: an agent's answer the tutor wrote, 15 minutes,
  nothing to open. The tutor picks the disguise, so the harder answers (one that cites a blog, one
  that hedges) actually come up. `a-check-lab-answer` is the same capability on the answer your own
  table's prompt got.
- **check note:** Every planted-claim example in the generator also appears in a study entry or the
  orientation reading: PlanetScale, Heroku, Railway's $5, Render's Postgres, Neon's compute,
  Fly.io's card rule. A learner who has done those routes may recognize the planted claims from
  memory. For a counting instance, plant claims about vendors or limits the learner has not met in
  this topic. If you can't, note in the record which planted claims the learner had already seen.

### `a-check-lab-answer`

- **serves:** `c-check-vendor-claims`
- **supports:** attempt
- **checks:** `c-check-vendor-claims`
- **artifact:** no external source. An agent's answer to the learner's table's session 11 lab
  prompt comparing cloud hosting providers, kept word for word. In the lab itself students run the
  prompt and sign up straight away, so by default the answer is a fresh rerun of the table's
  prompt, or a tablemate's answer, that names at least one vendor the learner has not yet visited
  or signed up for; the learner's own lab answer serves only if they had not opened any vendor it
  names before writing the note. 15 minutes to write the plan, plus however long carrying it out
  takes.
- **verified:** 2026-10-01
- **learner does:** with the answer in hand and before opening any vendor page it names or asking
  the agent anything more about it, writes alone in a note how they will find out which of its
  claims about free tiers, limits and credit cards still hold, claim by claim, and what they will
  add to the table's prompt next time. Then carries the plan out, writing beside each claim what
  the vendor's page said, with the address. Brings the tutor the answer, the note as first
  written, and what they found.
- **tutor role:** none
- **tutor does:** when first offering this, tells the learner to write the note before opening any
  vendor page, and to write at its top anything they looked at for help. Afterwards, confirms the
  note came first. Before sending to the adjudicator, checks each claim in the answer on the
  vendor's own pages that day and writes the key: which claims hold, which are stale, and any card
  requirement the answer left out, with addresses. If the answer has no stale claim and no omitted
  card requirement at all, tells the adjudicator so: the plan is still judged on whether it would
  have caught one. Sends the adjudicator the answer, the note as first written, any help noted,
  the key, and, marked as what happened afterwards, what the learner found. Labels the attempt
  `a-check-lab-answer/<vendors, joined with +>`.
- **done when:** criterion met with no help. The plan is judged as first written, not on what the
  checks turned up.
- **kind:** generator
- **generator:** the material is whatever the learner's agent said in the lab, so no two instances
  match and nobody sets the difficulty. Hold fixed: the note is written before any vendor page is
  opened and before the agent is asked anything more; the answer is kept word for word. Claims
  about a vendor the learner had already visited or signed up for before writing the note are left
  out of the ruling (the tutor marks them in the key), and there is no instance if that leaves no
  claim about free tiers, limits or cards; the tutor then supplies a rerun or a tablemate's answer
  instead. A note that
  says only "ask the agent if it's sure" or "check another AI" is an instance, and a miss. On
  review visits, use a fresh answer (a rerun of the table's prompt, or a tablemate's answer the
  learner hasn't checked).
- **worked example:** no tutor is present, so nobody offers one. If the learner stalls, they may
  look at `tasks/check-2025-guide-claims.md`, which holds no answers (its key is in a separate
  file the learner is never sent); they write at the top of the note that they did, and the
  attempt is recorded `unaided: no`.
- **doesn't show:** that the note came first rests on the learner's say-so. Whether the answer
  happened to contain a withdrawn free tier, a changed limit or a missing card requirement is
  luck, so a pass may never have faced one; the plan is judged on whether it would have. The
  learner wrote the prompt with their table, so the prompt addition may be the table's idea.
- **offer as:** the real thing: an answer to your own table's prompt, on vendors you haven't
  looked at yet, and you find out what's still true before you'd act on it. Any time after the
  session 11 lab, with a fresh run of the prompt or a tablemate's answer. `a-plan-claim-checks`
  is the one to take before it.
- **check note:** When you write the key, record the kind of page that settles each claim (pricing
  page, free-plan docs, trial page, billing docs). Send the adjudicator the "would catch" rule from
  `a-plan-claim-checks`'s generator along with the key, so that this check and that one are judged
  to the same standard. A plan that says only "check the pricing page" does not catch a claim
  settled only in trial or billing docs.

### `a-study-hatchable-traps`

- **serves:** `c-weigh-hosting-plans`
- **supports:** deepen
- **artifact:** Hatchable, "Free web hosting in 2026",
  https://hatchable.com/articles/state-of-free-web-hosting-in-2026 (updated 2026-08-21, no author
  named; checked 2026-10-01). About 2,800 words in all (the page says "13 min read"). Read only:
  the subsection Free backend hosting: somewhere to run server code (about 245 words) and the one
  after it, Where Hatchable fits (about 185); The traps to watch for (about 195); and the FAQ
  answer Do I need to provide a credit card for free hosting? (about 85). About 710 words: 5
  minutes of reading in a 15-minute sitting. Skip the rest, including the managed Postgres
  subsection, which belongs to the database-hosting topic. What it gives: six traps (a free trial
  dressed up as a free tier, 12-month free tiers that start billing, free-with-ads subdomains,
  free-for-personal-use-only, unused free machines reclaimed, cold starts on free app hosting);
  backend hosts' spin-down and hour budgets; and where cards are asked for. Two sentences from the
  skipped parts that the tutor quotes as context: "the 'free' total is three or four accounts with
  three or four sets of limits" (the managed Postgres subsection) and "Export your own dumps."
  **Warn the learner before they start: the article is written by a hosting vendor, and it
  recommends itself** (its list of recommendations puts Hatchable against "Small app with a
  database"). Where Hatchable fits says only that it "is not a Python or Docker host and does not
  run long-lived processes". Hatchable's own "Rules & restrictions",
  https://hatchable.com/docs/developers/restrictions (checked 2026-10-01), is read for two lines
  only: "The runtime is a sandbox, not Node" and "No `npm install`. Dependencies are never
  installed." Express is an npm package that runs as a Node server, so a Problem Set 2 backend
  would have to be rewritten as Hatchable handlers: a port, not a deploy, and code written for one
  vendor's SDK, which is deep lock-in. The article's dated claims are claims to check, not facts
  to carry (`a-watch-claims-checked` uses them that way).
- **verified:** 2026-10-04
- **learner does:** before reading, writes the five things the goal asks them to compare (sleep;
  what happens past a limit; card required, and what a card on file risks; whether their agent can
  reach the host; how hard it is to move). Reads the assigned parts, and for each trap writes
  which of the five it is about, or none. Then finds the sentence in Where Hatchable fits that
  shows the recommendation can't be taken as given for their app, reads the two restriction lines
  with the tutor, and says what their backend would have to become to run there. Last, for their
  own app's frontend and backend on two vendors, lists the accounts, what would be copied between
  them, and the places they would look when it broke.
- **tutor role:** socratic questioner
- **tutor does:** gives the vendor warning before the reading. Stays out until the learner has the
  traps mapped. Asks near-miss questions: "a 12-month free tier that starts billing; is that about
  a limit, or about a card?" (both: it bills the card it already has); "cold starts: is that the
  same as the app being switched off?" If the learner hasn't found the long-lived-processes
  sentence, asks what their Express server does between requests. On the two restriction lines,
  lets the learner arrive at "rewrite it", then asks how hard that code would be to move back off
  Hatchable (lock-in). On the accounts list, asks what the frontend needs to know to reach the
  server, and quotes the "three or four accounts" sentence as context. If the learner starts
  weighing where the database goes, says that belongs to the database-hosting topic. Says at the
  end that the article says nothing about an agent reading a host's logs or changing its settings;
  `a-judge-plan-weighings` and the checks supply that in the terms.
- **done when:** every trap is mapped to one of the five or to none; the learner has quoted the
  long-lived-processes sentence and, from the restrictions page, said that their app would need
  its backend rewritten to run on Hatchable, and that this is lock-in; their accounts list names
  at least the server's address going into the frontend's build and two places to look. No
  `checks`: the article did the comparing.
- **offer as:** a real, current, readable survey (updated August 2026) of what free hosting
  costs you, and a lesson in reading one written by an interested party: the vendor's own list
  recommends it for a kind of app its own docs show your app would have to be rewritten to
  become. About 710 words plus two lines of its docs, 15 minutes, nothing to run.

### `a-predict-overage-outcomes`

- **serves:** `c-weigh-hosting-plans`
- **supports:** deepen
- **artifact:** two pages, read in this order as one sitting, because the second is where the
  prediction made on the first gets checked. Both checked 2026-10-01.
  1. ServerlessHorrors, "$104,500" (Netlify bill),
     https://serverlesshorrors.com/all/netlify-104k/ (February 2024, about 470 words). A static
     site on Netlify's free plan was hit by a DDoS attack that used 190 TB of bandwidth in four
     days, and Netlify billed $104,500; it first offered a 95% discount, and after the story spread
     the CEO waived the charge. **This is history**: Netlify's free plan now has a hard limit with
     no overage (Netlify's docs, "Credit-based pricing plans", last updated Sep 1, 2026,
     https://docs.netlify.com/manage/accounts-and-billing/billing/billing-for-credit-based-plans/credit-based-pricing-plans/).
     Say so before the learner reads.
  2. Render, "Deploy for Free", https://render.com/docs/free, only its sections on free web
     services and on what happens at each limit. "Render spins down a Free web service that goes
     15 minutes without receiving any inbound traffic", and it takes about a minute to come back.
     "If you consume all of your Free instance hours during a given month, Render suspends all of
     your Free web services until the start of the next month." On bandwidth: "If you consume all
     of your outbound bandwidth during a given month, Render bills you for a supplementary amount.
     If you haven't added a payment method, Render instead suspends all of your Free services for
     the remainder of the month." Build minutes work the same way, except that without a payment
     method Render disables new builds instead. And Static sites: "Static sites are free to deploy
     on Render. As with web services, they count against your monthly included amounts of
     outbound bandwidth and pipeline minutes." Read only the sections Spinning down on idle,
     Monthly usage limits (with Free instance hours, and Bandwidth and build pipeline) and Static
     sites; skip the rest, including Free Postgres, which belongs to the database-hosting topic.
     Settling lines: spin-down is named only for web services, so the static frontend doesn't
     sleep; "suspends all of your Free services" covers the static site too in the forum case.
  10 to 15 minutes.
- **verified:** 2026-10-04
- **learner does:** reads the story. Before opening Render's page, writes predictions for their
  own app's frontend and backend on Render's free plan in three cases: nobody visits for an hour,
  then a grader does; the app is shared on a busy forum and its traffic goes far past the free
  bandwidth; the same, with a card on the account. For each, says whether the frontend and the
  backend sleep, stop, keep running, or cost money. Then reads Render's sections and marks each
  prediction right or wrong, quoting the sentence that settles it. Ends with one sentence on what
  having a card on file risks.
- **tutor role:** socratic questioner
- **tutor does:** gives the "this is history" framing first. Insists the three predictions are
  written before Render's page is opened. On each wrong prediction, asks what the learner had
  assumed rather than correcting it. On the card case, asks what the difference between the two
  forum cases came down to (only whether a card was on file). Leaves the database to the
  database-hosting topic.
- **done when:** three predictions were recorded before the reveal and each is marked with a quoted
  sentence, including that the static frontend doesn't sleep; and the learner can say that a card
  on file turns a stop into a bill on Render's terms. No `checks`:
  one vendor's terms were laid out for them.
- **offer as:** the vivid one: a real $104,500 bill (since waived, and no longer possible on that
  plan) and then a real vendor's terms, where you predict before you read. About one vendor and
  about what happens past a limit and with a card, more than about choosing. 10 to 15 minutes.
  Pick `a-judge-plan-weighings` for a whole comparison.

### `a-judge-plan-weighings`

- **serves:** `c-weigh-hosting-plans`
- **supports:** deepen
- **artifact:** `tasks/judge-plan-weighings.md`, written for this topic, used as a bank of eight
  students' choices, one per sitting. Its header (about 450 words) gives a class-project app with
  a React frontend and an Express server (its database is left to the database-hosting topic);
  two plans (one vendor for both, and a separate vendor for each); and three made-up vendors'
  free-tier terms modeled on terms
  real vendors offered on 2026-10-01, each covering sleep, what happens past a limit, card, agent
  access (a command-line tool, an MCP server, what it can and can't do) and moving. Each choice
  `v1` to `v8` is about 20 to 180 words and reads alone. The key, in its own file for the tutor only
  (`tasks/judge-plan-weighings-key.md`), has a verdict per choice and splits the differences into
  those a complete answer must name for this app and those present in the terms but not deciding
  for twenty users. 10 to 15 minutes a sitting. Nothing to run.
- **kind:** bank
- **bank:** the eight choices in `tasks/judge-plan-weighings.md`, named `v1` to `v8`. Cases:
  complete, choosing H `v1`; complete, choosing S `v2`; claims the terms don't support `v3`, `v5`;
  misses the extra vendor's cost and agent access `v4`; a card treated as a requirement rather
  than a risk `v6`; no case for the other plan `v7`; a supported workaround that still misses the
  card and moving `v8`. To pick the next, run
  `served.mjs cloud-hosting-2026-10 c-weigh-hosting-plans`, take a choice not yet served, and
  prefer a case the learner hasn't met; `v1` or `v2` first gives the learner a complete answer to
  measure the others by, and `v6` should come early, after `v1`. Label the attempt
  `a-judge-plan-weighings/<choice>`, for example `a-judge-plan-weighings/v6`. Stop when done when
  has been met on two or three sittings with different cases, and offer `a-weigh-described-plans`;
  using up the bank is not the target.
- **verified:** 2026-10-04
- **learner does:** reads the header and the one choice served, then says which of the
  criterion's parts it misses, if any: a difference that matters, the cost of the extra vendors,
  a claim the terms don't support, the case for the other plan. Points to the line in the terms
  for each, and says one thing the choice should have said (or, if it misses nothing, why it is
  complete).
- **tutor role:** critic
- **tutor does:** shows the header and the one choice, never the key file. Takes the learner's
  verdict before commenting. Where it disagrees with the key, asks the learner to point to the
  line in the terms that supports, or doesn't support, what the student said. If the learner
  counts a missing item from the key's second group as a miss, asks why it would decide anything
  for twenty users. If this choice's partner in the key has been served before, asks how the two
  differ (for `v6` after `v1`, "both chose H; what does each say about a card?"). For `v6`, makes
  sure the difference between a card that is required and a card that lets a vendor bill comes
  out. Checks, on any item, whether agent access and the secrets copied between vendors came up,
  the two things students most often leave out. If the verdict still differs from the key after
  one such question, gives the key's verdict and its what-decides-it line, and moves on.
- **done when:** the learner's verdict on this choice matches the key, each miss tied to a line in
  the terms and covering at least the misses in the key's verdict column, and the one thing they
  say it should have said is in the key's must-name group (or, for `v1` and `v2`, they say why it
  is complete). For an unsupported claim (`v3`, `v5`, `v6`),
  "nothing in the terms says this" is the line to point to. No `checks`: judging someone else's choice is
  not making one, and the terms were laid out for comparison.
- **offer as:** one student's choice at a time, judged against terms laid out for you: the only
  study route that touches all five differences, the extra vendors, and the case for the other
  plan, including agent access, which no reading in this topic covers. Made-up vendors, so nothing
  here goes stale. 10 to 15 minutes, nothing to run.
- **check note:** For `v6`, the line to point to is not "nothing in the terms says this" but the
  terms' own first line, "No vendor needs a card to sign up": the claim is contradicted, not merely
  unsupported. Accept either, but prefer the quoted line, since it is the habit of pointing to what
  the terms say that this item is for.

### `a-weigh-described-plans`

- **serves:** `c-weigh-hosting-plans`
- **supports:** attempt
- **checks:** `c-weigh-hosting-plans`
- **artifact:** no external source. An app, two plans and made-up vendors' free-tier terms,
  written by the tutor per the generator below. 15 to 20 minutes.
- **verified:** 2026-10-01
- **learner does:** reads the app, the plans and the terms, then writes alone which plan they would
  choose and why: every difference in the terms that would matter for this app, what the extra
  vendors add in accounts, secrets and places to look when something breaks, and the strongest
  case for the plan they didn't choose. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and writes the key into the record before
  showing anything: each difference that matters and what it is, what the extra vendors add, any
  difference in the terms that doesn't matter for this app (and so may be named but not leaned on),
  and the strongest case for each plan. Shows the app, the plans and the terms. Waits, writing down
  any help word for word. Sends the adjudicator the instance, the key, the learner's answer
  verbatim and every piece of help, with the reminder that which plan they chose is not part of the
  criterion. After the ruling, tells the learner what was missed or unsupported. Labels the attempt
  `a-weigh-described-plans/<twist>`. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed: the app is a class project with a React frontend and an Express server,
  used by about twenty people, built by someone working through a coding agent; its database is
  never part of the plans, the terms or the key. Plan one puts the frontend and backend with one
  vendor; plan two uses a separate vendor for each. Vendors are made up. Harbor, Brightpage and
  Kettle from `tasks/judge-plan-weighings.md`, with the
  terms given there, are for the worked example only, since `v1` and `v2` already weigh them in
  full. A counting instance invents new vendors on the same pattern, or keeps those names with
  terms changed on at least three of the five dimensions so that the key differs from that
  file's. Each vendor's terms are four to six bullets, always covering: whether anything
  sleeps and how long it takes to wake; what happens past each limit (paused, suspended, stopped
  when credit runs out, billed with a card); whether a card is required, and what a card on
  file allows the vendor to bill; agent access (whether there is an official command-line tool, an
  MCP server or an API, and what it can and can't do: deploy, set environment variables, read
  logs); and moving (standard tools and exports, or something vendor-specific). What
  varies: the terms, and the twist:
  - `lopsided` (Easy): one plan is better on four of the five, and the strongest case for the
    other is still real.
  - `balanced` (Medium): each plan wins on at least two of the five.
  - `agent-gap` (Medium): the single vendor's agent tool can't read the backend's logs, or one
    split vendor has no command-line tool or MCP server at all, only a dashboard.
  - `card-trap` (Hard): every vendor signs up without a card, but one bills overages once a card is
    added (for example, after the learner adds one to unlock a feature); or one asks for a card
    only to verify identity and can't bill it. A pass has to tell these apart.
  - `irrelevant-difference` (Hard): one large difference that doesn't matter for twenty users (a
    bandwidth allowance of 100 GB against 1 TB, a region list, team seats); leaning on it as a
    reason counts as naming something the terms don't support for this app.
  Difficulty as marked. An attempt meant to count runs at Medium or Hard. Across visits, serve
  `agent-gap` and `card-trap` at least once each, reading the labels `served.mjs` returns.
- **worked example:** work one instance aloud, either an Easy one or the Harbor, Brightpage and
  Kettle terms if the learner hasn't done `a-judge-plan-weighings`, going through the five
  differences one at a
  time and saying for each what the terms say for each plan and whether it matters for twenty
  users, then listing what the extra vendors add, then arguing the other plan's case as hard as
  possible. At the first level of help on a real attempt, ask only "what happens on each plan when
  nobody has visited for an hour?"
- **doesn't show:** the terms are stated plainly in a few bullets each, so a pass doesn't show the
  learner could find them on real vendors' pages, where they are spread over pricing, docs and
  billing pages and agent access is on a page of its own. Vendors are made up, so a pass says
  nothing about real ones. The two plans are always one vendor against a vendor for each part, as
  the criterion says, and the database is left out. The learner knows a check is on.
- **offer as:** the check that's available now: two plans the tutor wrote, 15 to 20 minutes,
  nothing to run, and the tutor picks the twist so the hard cases (a card that can be billed once
  added, an agent that can't see the backend's logs) actually come up. `a-weigh-lab-plans` is the same
  capability on two plans from your own lab.
- **check note:** On an `irrelevant-difference` instance, the generator calls leaning on the large
  irrelevant difference "unsupported", but the criterion's clause is about what the terms support,
  and a true difference is supported. The study key for `a-judge-plan-weighings` accepts leaning on
  an accurate non-deciding item. When you send the instance to the adjudicator, say what the twist
  was. Ask it to rule against the criterion as written: a true but irrelevant reason is not by
  itself a miss, while a claim the terms contradict (that twenty users would reach the limit, for
  instance) is.

### `a-weigh-lab-plans`

- **serves:** `c-weigh-hosting-plans`
- **supports:** attempt
- **checks:** `c-weigh-hosting-plans`
- **artifact:** no external source. Two plans for the learner's own Problem Set 2 app taken from the
  session 11 lab (their agent's answer and a tablemate's, or one answer's two options), one putting
  the frontend and backend with a single vendor and one using a separate vendor for each, with the
  vendors' free-tier terms as the tutor gathers them from the vendors' own pages. The database is
  left out. 20 minutes, plus the tutor's preparation.
- **verified:** 2026-10-04
- **learner does:** reads the two plans and the terms sheet, then writes alone which plan they would
  choose for Problem Set 3 and why, as in `a-weigh-described-plans`. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, picks two plans from the lab that fit the criterion's shape;
  if none does, builds the second from the first (the single vendor's own two services, or a
  separate vendor for each part from the vendors the lab answers named). For each vendor, reads its own current
  pages and writes a terms sheet in the bullets of `a-weigh-described-plans`'s generator, with the
  address and date of each page; the sheet must include agent access, from the vendor's own docs
  on its command-line tool, MCP server or API (for example, on 2026-10-01: Render's MCP server,
  https://render.com/docs/mcp-server, which can create services, set environment variables, read
  logs, but cannot delete resources or change most settings; Netlify's MCP server and CLI,
  https://docs.netlify.com/build/build-with-ai/netlify-mcp-server/). Where a vendor's pages don't
  settle a term, writes "not stated by the vendor" rather than guessing. Leaves database terms out
  of the sheet and the key. Writes the key as in `a-weigh-described-plans`. Waits during
  the attempt, writing down help word for word. Sends the adjudicator the plans, the sheet, the
  key, the answer and the help. Labels the attempt `a-weigh-lab-plans/<single vendor>-vs-<split
  vendors, joined with +>`. A remark about where the database goes is neither credited nor counted as a false gap or an
  unsupported claim: the tutor tells the adjudicator to disregard it, and the learner that it
  belongs to database-hosting.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is whatever the lab produced, so nobody sets the difficulty. Hold
  fixed: one single-vendor plan and one plan with a separate vendor for the frontend and the backend; terms from the vendors' own
  pages on the day, never from an agent's answer; every sheet covers all five differences,
  including agent access, or says the vendor doesn't state it. On review visits, use different
  vendors, or the same vendors with terms re-read that day, since they may have changed.
- **worked example:** none during the attempt. If the learner stalls, the first level of help is
  "what happens on each plan when nobody has visited for an hour?", and the attempt is recorded
  `unaided: no`.
- **doesn't show:** the tutor gathers the terms, so a pass doesn't show the learner could pull them
  from vendor pages themselves; `c-check-vendor-claims` covers finding out, and this covers
  weighing. Which twists come up is luck: real terms may have no card trap or agent gap. The key
  rests on the tutor's reading of vendor pages on one day.
- **offer as:** the real decision you face in Problem Set 3, on the vendors your own lab turned up,
  with their real terms gathered that day. Best after the lab and before you sign up for the
  plan you'll use. `a-weigh-described-plans` is the one to take before the lab.

### `a-w-deploy`

- **origin:** generated
- **serves:** `w-deploy`
- **checks:** `w-deploy`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-build`

- **origin:** generated
- **serves:** `w-build`
- **checks:** `w-build`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-static-host`

- **origin:** generated
- **serves:** `w-static-host`
- **checks:** `w-static-host`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-server-host`

- **origin:** generated
- **serves:** `w-server-host`
- **checks:** `w-server-host`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-database-host`

- **origin:** generated
- **serves:** `w-database-host`
- **checks:** `w-database-host`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-free-tier`

- **origin:** generated
- **serves:** `w-free-tier`
- **checks:** `w-free-tier`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-idle-sleep`

- **origin:** generated
- **serves:** `w-idle-sleep`
- **checks:** `w-idle-sleep`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-cold-start`

- **origin:** generated
- **serves:** `w-cold-start`
- **checks:** `w-cold-start`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-overage`

- **origin:** generated
- **serves:** `w-overage`
- **checks:** `w-overage`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-lock-in`

- **origin:** generated
- **serves:** `w-lock-in`
- **checks:** `w-lock-in`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-domain`

- **origin:** generated
- **serves:** `w-domain`
- **checks:** `w-domain`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-dns`

- **origin:** generated
- **serves:** `w-dns`
- **checks:** `w-dns`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-https`

- **origin:** generated
- **serves:** `w-https`
- **checks:** `w-https`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-cdn`

- **origin:** generated
- **serves:** `w-cdn`
- **checks:** `w-cdn`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-instance`

- **origin:** generated
- **serves:** `w-instance`
- **checks:** `w-instance`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
