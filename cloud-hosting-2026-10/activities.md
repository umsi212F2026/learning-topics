# Activities: cloud hosting

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-place-app-parts` | say which kind of host each part of an app needs, and whether a hosting plan covers them all | Given an app's parts, such as a React frontend, an Express backend and a SQLite database, and a hosting plan listing each vendor and what it offers, says which part each vendor would host, and names any part the plan leaves without a host or puts on a host that cannot run it, or says that every part is covered. It passes when every gap and mismatch is found and nothing is named that isn't one, including for a plan where one vendor hosts more than one part, or where the backend serves the built frontend itself. |
| `c-check-vendor-claims` | find out whether what an agent says about a hosting vendor is true today | Given an agent's answer comparing hosting vendors, says how they would find out which of its claims about free tiers, limits and credit cards still hold. It passes when what they describe checks each claim against the vendor's own current pages, not against the agent, a blog post or a forum; would catch a free tier the vendor has since withdrawn, a limit that has changed, and a credit card requirement the answer left out; and says what they would add to the prompt so that every claim in the next answer comes with what they need to check it. Asking the agent whether it is sure does not meet it. |
| `c-weigh-hosting-plans` | choose between hosting plans for an app, knowing what each would cost | Given two hosting plans for the same app, one putting every part with a single vendor and one using a different vendor for each part, along with each vendor's free-tier terms, chooses one and says why. It passes when they name each difference in the terms that would matter for a class project with few users (whether the app sleeps, what happens when it passes a limit, whether a credit card is required and what having one on file risks, whether their agent can reach the host to change its settings and read its logs, and how hard it would be to move); say what the extra vendors add in accounts, secrets and places to look when something breaks; name nothing the terms don't support; and state the strongest case for the plan they didn't choose. Which plan they choose is not part of it. |

## Coverage

<!--
  Derivation convention: an activity carrying `checks` sits only in the `checks` cell, never in
  `study`. Activities whose `serves` is `all` sit on the `o-orientation` row only.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `o-orientation` | `a-read-odin-deployment` | `a-dry-run-hosting-asks` | |
| `c-place-app-parts` | `a-read-fso-serve-dist`, `a-judge-plan-coverage` | `a-place-described-plan`, `a-place-lab-plan` | |
| `c-check-vendor-claims` | `a-watch-claims-checked`, `a-check-2025-guide-claims`, `a-sort-claim-sources` | `a-plan-claim-checks`, `a-check-lab-answer` | |
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
     (last modified Apr 29, 2025). Read Summary (about 320 words), the short Deeper dive opening
     (about 50), Hosting files (about 280) and Static vs. dynamic content (about 350): about 1,000
     words. Skip Communicating through HTTP (the web backends topic covered requests and
     responses) and Next steps. No code anywhere. What it gives that Odin doesn't: the static web
     server, which "sends its hosted files as-is to your browser", as against the dynamic one with
     an application server and a database; and that hosting a site means putting its files on a
     machine that is always on and always connected, because a laptop isn't.
  2. **Then:** The Odin Project, "Deployment" (Node path),
     https://www.theodinproject.com/lessons/node-path-nodejs-deployment. Read from Introduction
     down to, and not including, the heading "Debugging and troubleshooting deployments": What are
     hosting providers?, Static vs dynamic sites, What is a PaaS?, How do PaaS services work?
     (Instances; Server instance and database instance; Databases; Domain names), Our recommended
     PaaS services (Railway.app, Render, Neon, Aiven) and Keep your secrets safe!. About 1,450
     words, no code blocks. Skip Debugging and troubleshooting deployments (debugging a deploy is a
     later topic), the Assignment and Additional resources.
  About 2,450 words in all: 20 minutes of reading inside a 50 to 60 minute session with the
  stops below.
  Words in place: across the two, deploy, static, server, database, free tier (Heroku's, ended
  2022), sleep ("put to sleep automatically after 15 minutes of inactivity", in Render's
  paragraph), instance (Odin's Instances section), domain (Odin's Domain names; MDN's Summary),
  credit card ("No credit card required", Neon and Aiven). Not named, and supplied by the
  vocabulary words: build, cold start, overage, lock-in, DNS, HTTPS, CDN. Odin is written for its
  own Node course, whose apps are rendered on the server, so its picture is two boxes (a server and
  a database) and it says Netlify and Vercel "are not the right tools for our back ends" without
  saying where a React frontend would go. MDN's static web server is the third box, which is why it
  comes first. The Databases paragraph on backups and the Keep your secrets safe! box touch on
  keeping data safe and on secrets, which are later topics; let them pass.
  **Vendor details in Odin that lag, as checked against the vendors' own pages on 2026-10-01:**
  - Railway: Odin says the trial is "a free one-time grant of $5 ... and the applications are never
    put to sleep", after which Railway "rolls you back to their limited trial, which you can only
    deploy database". Railway's docs (https://docs.railway.com/reference/pricing/free-trial) now
    say the one-time $5 trial lasts up to 30 days and then "reverts to the Free plan", which gives
    "$1 of free credit per month" that "does not roll over".
  - Render: Odin says "the lowest spec databases cost $7 each" and, a few lines later, that "You can
    only have one active free database at a time, which expires 30 days after creation". The page
    contradicts itself. Render's docs (https://render.com/docs/free) have a free Postgres that
    expires 30 days after creation, with a 14-day grace period before it is deleted.
  - Neon: Odin lists "10 projects" and "24/7 for your main compute". Neon's pricing page
    (https://neon.com/pricing) now lists 100 projects, 100 compute-hours per project, and compute
    that scales to zero after 5 minutes idle, which "cannot be turned off".
  - Aiven: Odin says "5 GiB of storage"; Aiven's page
    (https://aiven.io/free-postgresql-database) says "1 GB storage, 1 GB RAM, 1 CPU per VM". Odin
    says "24/7 for all database services"; Aiven says the free service "powers off after a period
    of inactivity (you'll be notified by email and in-platform beforehand)", and its docs
    (https://aiven.io/docs/platform/concepts/free-plan, updated 2026-09-08) say it may "Power off
    free services with no initial usage within the first few hours" and "Power off free services
    with no continuative activity"; "You can power them back on at any time." Odin's "No credit
    card required" still holds: "You don't need a credit card to create a free service and you can
    use them indefinitely free of charge." Odin names Redis; Aiven's free list now says Valkey.
- **verified:** 2026-10-01
- **learner does:** reads MDN first, with their Problem Set 2 app's folder open beside the page,
  then Odin. Stops at six points and answers before reading on; "I don't know yet" is an honest
  answer:
  1. MDN, after Summary: which of their app's parts could a static web server send as it is, and
     which needs something running?
  2. Odin, after Static vs dynamic sites: their app is dynamic, but which of its parts is made of
     files that are the same for everyone?
  3. Odin, after Server instance and database instance: **sketches their own app as three boxes,
     frontend, backend and database, and labels each with the kind of host it needs** (one that
     sends files as they are; one that keeps a program running; somewhere the data lives once it
     leaves the laptop). Then says where the SQLite file sits in that sketch, and whether one vendor
     could hold more than one box.
  4. Odin, after Domain names: what address a visitor would type to reach their app on the first
     day, before they buy any name.
  5. Odin, after each vendor in Our recommended PaaS services: which of their three boxes that
     vendor could hold, and one detail in the paragraph they would want to check before relying
     on it.
  6. At the end, looking away from both pages: says in three or four sentences what they would
     need to decide in Problem Set 3, before any deploy, and what they would ask their agent for in
     the session 11 lab.
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with a near-miss question rather than a
  verdict ("you said the frontend needs a server host because it's React; once it's built, what
  is left in `dist/` that has to run on the host?"). At stop 3, checks that the sketch puts the
  built frontend on a host that sends files, the Express server on one that keeps it running, and
  the SQLite file next to the server, since it is a file the server opens and not a service of its
  own; if the learner asks whether the backend could send the frontend's files itself, says yes
  and that `a-read-fso-serve-dist` shows how. At stop 5, **flags each lagging vendor detail listed
  under artifact as the learner reaches it, rather than dropping the page or correcting it
  silently**: names the detail, says what the vendor's own page said on 2026-10-01 and where, and
  asks the learner which they would trust and why. That is the habit `c-check-vendor-claims` builds,
  met here on a page that was right when it was written. Points out that Odin's own Render
  paragraph says two different things about databases. Does not explain secrets, backups or
  debugging; says each is a later topic. Makes no change to the learner's app.
- **done when:** each of the six stops has an answer tied to the learner's own app, the sketch has
  three labeled boxes with the SQLite file placed, and at stop 5 the learner has named, for at
  least one vendor, a detail they would check and where. No `checks`: the readiness indication
  `o-orientation` is ruled on is taken in `a-dry-run-hosting-asks`, which follows.
- **offer as:** this topic's orientation, deliberately one entry holding a sequence: a short MDN
  page that supplies the static web server, then Odin's lesson, which supplies hosting providers,
  PaaS, instances, domains and four real vendors, with the debugging half left for a later topic.
  About 2,450 words, free, 50 to 60 minutes with the stops. Odin's vendor details are a year or so
  behind in places, and the tutor flags them as they come up; that is part of the lesson, not a
  defect in the choice. Followed by `a-dry-run-hosting-asks`.

### `a-dry-run-hosting-asks`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** no external source. The learner's three-box sketch and their answers from
  `a-read-odin-deployment`, still in front of them. 10 to 15 minutes. Nothing needs to be running.
- **verified:** 2026-10-01
- **learner does:** three short rehearsals, none of them judged, each answered in a sentence or
  two. First, the tutor describes a made-up app's three parts and one vendor's offer in a line, and
  the learner says which part that vendor could host, or none. Second, the tutor, speaking as a
  coding agent, makes one claim about a vendor's free tier, and the learner says where they would
  look to find out whether it is true today (or, for a recommendation, what it leaves out and
  where they would find that). Third, the tutor gives one line of terms from each of
  two plans, and the learner says one difference between them that would matter for a class
  project. Then answers the question the tutor puts: with your sketch and the reading beside you,
  could you now attempt these three things for real: saying which kind of host each part of an
  app needs and whether a plan covers them all; finding out whether what an agent says about a
  hosting vendor is true today; and choosing between two hosting plans knowing what each would
  cost you?
- **tutor role:** explainer
- **tutor does:** sets the three rehearsals from the generator below and grades none of them. If
  an answer shows a misunderstanding (the frontend needing a server host because it is React; the
  agent's word, or a blog's, as the place to look; "free" as the only difference worth naming),
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
- **generator:** vary the made-up app and the three items; hold the rest fixed. The app is small,
  with a React frontend, an Express server and a database, used by a class (a study-group finder,
  a club sign-up sheet, a recipe box, a used-textbook board). Rehearsal one is one plan line from
  `a-place-described-plan`'s generator at Easy: one vendor, one offer, one part. Rehearsal two is
  one claim from `a-plan-claim-checks`'s generator of kind `withdrawn` or `changed`, and the
  question is where they would look to find out whether it is true today. If the tutor uses a
  `card-omitted` claim instead, it is given as a recommendation ("I'd go with Fly.io's trial") and
  the question becomes what the recommendation hasn't said that they would want to know, and where
  they would find it. Rehearsal three is
  one dimension from `a-weigh-described-plans`'s generator (sleep, past a limit, card, agent
  access, or moving), one line per plan, at Easy. Fixed: three rehearsals in that order, none
  graded, then the readiness question word for word. Difficulty doesn't vary: this settles an
  indication, not a capability.
- **worked example:** if the learner freezes on a rehearsal, the tutor answers a different made-up
  one aloud in two or three sentences, then hands the original back.
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about any of the three capabilities: every rehearsal is helped, ungraded and of the
  easiest kind, and a one-sentence answer never has to be complete. It shows nothing about the
  fifteen words, which have their own supply.
- **offer as:** the short step that closes orientation, after `a-read-odin-deployment`. Not an
  alternative to it: the reading gives you the shape, and this is where you say whether you have
  it. 10 to 15 minutes, nothing to run.

### `a-read-fso-serve-dist`

- **serves:** `c-place-app-parts`
- **supports:** deepen
- **artifact:** Full Stack Open, part 3b, "Deploying app to internet",
  https://fullstackopen.com/en/part3/deploying_app_to_internet (University of Helsinki; free, no
  account; checked 2026-10-01). Three sections only: Frontend production build, Serving static
  files from the backend, and The whole app to the internet. The sections contain commands and
  short code; the one line that matters is `app.use(express.static('dist'))`, which makes the
  Express server send the frontend's built files itself, so frontend and backend are at the same
  address. Skip everything about Fly.io and Render setup (that is how to deploy, past this topic's
  depth, and its vendor details may lag like Odin's), Same origin policy and CORS, and Proxy. 20
  to 25 minutes.
- **verified:** 2026-10-01
- **learner does:** reads the three sections without running anything. Then, on paper or in a
  note, draws two arrangements of their own Problem Set 2 app: (a) the built frontend on a static
  host and the Express server on a server host; (b) the Express server sending the built frontend
  itself. For each, labels every box with the kind of host it needs and draws where the SQLite
  file is. Then answers: in (b), what does the plan no longer need? If a classmate's plan used
  arrangement (b) and named no static host, would that be a gap? If a plan used arrangement (a) and
  put the Express server on a host that only sends files, what would happen when the page asked
  for data?
- **tutor role:** socratic questioner
- **tutor does:** stays out of the reading unless asked; if the learner stalls on the code, says
  only that `npm run build` makes a folder of plain files and `express.static('dist')` tells the
  server to send them. On the drawings, asks near-miss questions ("in (b) the frontend has no host
  of its own; is it unhosted?"; "in (a), could the static host also run the server if it's the
  same company?"). Does not get into how the page finds the server's address in (a); that is
  config, a later topic.
- **done when:** both drawings label each part with the kind of host it needs and place the SQLite
  file with the server, and the learner says that a missing static host in (b) is not a gap and an
  Express server on a files-only host is a mismatch. No `checks`: the arrangement was shown to
  them, and their own app is one they already know.
- **offer as:** the one candidate about the arrangement the criterion singles out, the backend
  serving the built frontend itself, shown in the course material many full-stack courses use.
  Some code on the page, though the learner runs none. 20 to 25 minutes. Pick
  `a-judge-plan-coverage` for ten plans to judge instead.

### `a-judge-plan-coverage`

- **serves:** `c-place-app-parts`
- **supports:** deepen
- **artifact:** `tasks/judge-plan-coverage.md`, written for this topic: Crumbs, a React, Express and
  SQLite app shaped like the learner's Problem Set 2 app; five made-up vendors, each saying in a
  line what it offers (a files-only host, a host that runs a program with a disk, a Postgres-only
  database host, a host that runs short functions and keeps nothing running, and an all-in-one);
  ten plans. The key is in its own file, `tasks/judge-plan-coverage-key.md`, for the tutor only.
  Six plans cover every part: the usual split, one where the backend serves
  the built frontend, one where a vendor hosts two parts, one that hosts the frontend twice, one
  that uses the functions host only for files, and one where the app has been switched to
  Postgres. Four fail: an Express server on a files-only host with the database left unhosted, a
  frontend with nothing to send it, a database left on a laptop, and a plan with two mismatches
  (an Express server on the functions host and a SQLite database on a Postgres host). 20 minutes.
  Nothing to run.
- **learner does:** reads the app and the vendors, then for each of the ten plans says which part
  each vendor hosts and names every gap and mismatch, or says every part is covered. Then states the
  rule they judged by.
- **tutor role:** critic
- **tutor does:** shows the task file and never the key file. Takes all ten answers and the
  rule before commenting on any. On each answer that disagrees with the key, asks what that vendor
  would actually do with the part it was given ("Brightpage gets the Express server; what does it
  do when a request for recipes arrives?") rather than giving the verdict. Makes sure `q3` against
  `q6`, `q4` against `q9`, and `q8` are discussed whatever the learner answered. If the learner
  raises whether a free host's disk keeps the SQLite file, says that is a good question for the
  topic on keeping hosted data safe, and counts the file as hosted here.
- **done when:** the learner's rule covers listing what each part needs, checking each vendor's
  offer against the part it was given, counting a part served by another part as hosted, and naming
  nothing that isn't a gap or mismatch; and they found both mismatches in `q4`. No `checks`: the
  ten plans are a contrast set read together, and the pairs answer each other. `q9` sits beside
  `q4` and says outright that the app was switched to Postgres, which points at what is wrong in
  `q4`; `q3` beside `q6` does the same for a frontend with no host of its own. A learner judging
  `q4` or `q6` with its partner in view is getting help no single cold plan gives, so a pass here
  doesn't show they would find the fault in a plan met alone. `a-place-described-plan` is that
  single cold plan. The set is also fixed and used up after one sitting.
- **offer as:** ten plans for one app, so the only thing that varies is the plan; the six that
  pass show six ways to cover an app, and the near-misses are the cases careful students most
  often get wrong (calling a backend-served frontend unhosted, flagging a vendor for a job it
  wasn't given). Made-up vendors, so nothing here goes stale. 20 minutes, nothing to run.

### `a-place-described-plan`

- **serves:** `c-place-app-parts`
- **supports:** attempt
- **checks:** `c-place-app-parts`
- **artifact:** no external source. A made-up app and hosting plan, written by the tutor per the
  generator below. 10 minutes.
- **verified:** 2026-10-01
- **learner does:** reads the app's parts and the plan, then writes alone, for each vendor, which
  part it would host, and then names every part left without a host or put on a host that cannot
  run it, or says every part is covered. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and writes the key into the record before
  showing anything: which part each vendor hosts, and every gap and mismatch, or "every part
  covered". Shows the app's parts and the plan. Waits, writing down any help word for word. Sends
  the adjudicator the parts, the plan, the key, the learner's answer verbatim and every piece of
  help. After the ruling, tells the learner what was missed or named wrongly. Labels the attempt
  `a-place-described-plan/<shape>`.
- **done when:** criterion met with no help, on a `backend-serves`, `shared-vendor`, `decoy` or
  `two-faults` instance.
- **kind:** generator
- **generator:** fixed: the app has a frontend, a backend and a database, described in a short
  list in the form of `tasks/judge-plan-coverage.md` (what each part is, what it needs to run, and
  for SQLite that it is a file the server opens). The plan names two to four vendors, each with a
  one- or two-line offer written as that file writes them: what it hosts and runs, and what it does
  not. Vendors are made up, so the key depends only on the stated offers. Brightpage, Kettle,
  Ledger, Spark and Harbor may be used for the worked example and for practice; a counting
  instance invents new vendor names on the same pattern and never reproduces any of `q1` to `q10`
  in `tasks/judge-plan-coverage.md`, which the learner may have judged with its key discussed. Whether a
  host's disk keeps data is never part of an offer and never part of the key. What varies: the app
  (a different one each attempt; its frontend is React or another framework built to static files,
  its backend Express or another long-running server, its database SQLite or Postgres), the
  vendors and their offers, and the plan's shape:
  - `split-clean` (Easy): one vendor per part, every part covered.
  - `one-gap` (Easy): one part left without a host.
  - `wrong-host` (Medium): one part on a host that cannot run it as the app is now (a long-running
    server on a files-only or functions-only host; a SQLite file on a database-only host; a
    Postgres database expected on a host that offers only a disk).
  - `backend-serves` (Medium): the backend sends the built frontend itself and no static host is
    named; every part covered, or with one unrelated gap or mismatch.
  - `shared-vendor` (Medium): one vendor hosts two or three parts as separate services; every part
    covered, or with one mismatch inside that vendor.
  - `decoy` (Hard): every part covered, but the backend sends the built frontend itself and the
    frontend is also put on a static host, or a vendor hosting two parts has a limitation that
    doesn't bear on either part it was given; either way it invites a false gap or mismatch.
  - `two-faults` (Hard): two gaps or mismatches of different kinds, at least one inside a vendor
    hosting more than one part.
  Difficulty as marked. **Only `backend-serves`, `shared-vendor`, `decoy` and `two-faults` count**,
  because each contains a case the criterion names (a vendor hosting more than one part, or the
  backend serving the built frontend) and the bar is one unaided pass. `split-clean` and `one-gap`
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
  vendor does what. Whether a host's disk keeps a SQLite file is left out on purpose and is not
  examined. The learner knows a check is on.
- **offer as:** the check that's available now: a made-up app and plan, 10 minutes, nothing to
  run, and the tutor picks the shape so the two cases the criterion names (a vendor hosting more
  than one part, the backend serving the frontend) actually come up. `a-place-lab-plan` is the
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
- **learner does:** gets from the tutor a list of their app's parts, and the plan with each
  vendor's offer stated in a line or two. Writes alone which part each vendor would host, and
  names every gap and mismatch, or says every part is covered. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, reads the learner's app (the learner need not see this) to
  list its parts as they are now: what the frontend builds to, whether the backend already sends
  the built frontend, and whether the database is a SQLite file or something else. Turns the
  answer into a plan: if it already says which vendor hosts which part, uses that; if it is a
  comparison, takes the vendors it recommends and assigns each to the part the answer suggests it
  for; if the answer suggests nothing for some part, assigns one of the vendors it names to that
  part the way a student reading the answer plausibly would, and records that the tutor did this.
  For each vendor in the plan, reads that vendor's own current pages and writes its offer in a
  line or two, as `tasks/judge-plan-coverage.md` writes them, with the address and date of each
  page used; the offer must not be the agent's description of it. If a vendor's pages don't settle
  whether it can run the part it was given, replaces it with another vendor the answer names whose
  pages do; if there is none, shows that part's line as "not judged: the vendor's own pages don't
  settle this", tells the learner to leave that part out, and leaves it out of the key, so the
  missing offer is never mistaken for a planted gap. Writes the key into the record from the
  offers. **Counts the instance only if the plan contains a vendor hosting more than one part, a
  backend serving the built frontend, or a gap or mismatch.** A plan that is the usual one vendor
  per part with every part covered is practice only; the tutor says so and offers
  `a-place-described-plan` for the counting attempt. Waits during the attempt, writing down any help word for word. Sends the
  adjudicator the parts, the plan with its offers, the key, the learner's answer and every piece
  of help. Labels the attempt `a-place-lab-plan/<vendors, joined with +>`.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is whatever the learner's agent proposed, so no two instances match
  and nobody sets the difficulty. Hold fixed: offers come from the vendor's own pages on the day,
  never from the agent's answer; the key comes from those offers and the app's code. Only a plan
  with a shared vendor, a backend-served frontend, or a gap or mismatch counts, for the reason
  above. Across visits, use a different agent answer each time (a tablemate's, or a fresh run of
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
  the vendors' own pages the tutor opens live. Three claims from the article, quoted:
  - "Render's free Postgres, for instance, expires 30 days after creation per its changelog, with
    a grace period to upgrade before deletion." (Render's own page on 2026-10-01:
    https://render.com/docs/free, 30 days and a 14-day grace period.)
  - On Neon and Supabase: "both have free tiers with a small database (hundreds of megabytes),
    compute that sleeps or pauses when idle, and no card". (Neon's pricing page,
    https://neon.com/pricing, says "no credit card required"; Supabase's pricing page,
    https://supabase.com/pricing, did not say either way on 2026-10-01.)
  - "Fly.io no longer has a general free tier for new accounts, only a short trial before
    pay-as-you-go." This sentence says nothing about a card or about how short the trial is;
    the article's FAQ says elsewhere that "Fly.io wants one once its short trial ends". Fly's own
    pages split the answer across two places. Its free-trial page,
    https://docs.fly.io/about/free-trial/, says the trial "includes 2 hours of machine runtime or 7
    days of access, whichever comes first", needs no card to start, and that "adding a card ends
    the free trial"; when it expires without one, "your apps will stop running". Its pricing page,
    https://docs.fly.io/about/pricing/, says "All organizations (except for Linked Organizations)
    require a credit card on file".
  And a fourth for the learner, also from the article's The traps to watch for: "Railway's
  $5/month credit is a trial, not a free tier. When you exceed it, you pay." Railway's own docs,
  https://docs.railway.com/reference/pricing/free-trial, on 2026-10-01: the trial is "a one-time
  grant of $5" for "up to 30 days", after which the account "reverts to the Free plan", which
  "provides $1 of free credit per month" that "does not roll over". So the article's sentence is
  stale twice over: the $5 is one-time, not monthly, and there is a standing free plan after it.
  (Flavio Copes, "Every hosting provider's free tier, side by side",
  https://flaviocopes.com/hosting-free-tiers/, data checked 2026-09-16, with disclosed affiliate
  links, gives Railway's "$1 of credit a month, no rollover" correctly; the tutor may point out
  afterwards that a careful dated table got it right and still isn't the page that settles it.)
  25 to 30 minutes.
- **learner does:** watches the tutor check the first three claims out loud in a browser, and
  interrupts whenever they disagree or can't follow. Before each check, says where they would look.
  Then checks the fourth claim themselves while the tutor watches, saying aloud where they are
  looking and why. At the end, says in their own words what made a page good enough to settle a
  claim, and writes one sentence they would add to a prompt so that an agent's answer comes with
  what they need to check each claim.
- **tutor role:** explainer
- **tutor does:** before the session, opens each vendor page above and confirms it still says what
  is quoted; if it doesn't, uses what it says now and tells the learner that the claim changed
  between the curation and today, which is the point. Checks each claim aloud, including false
  starts made on purpose and named as such: for the first, searches the claim and lands on a blog
  post, then says why that doesn't settle it and goes to Render's own docs; for the second, finds
  Neon's sentence and then fails to find Supabase's on its pricing page, and says that an answer
  the vendor's pages don't give is "I'd find out at sign-up", not the article's word; for the
  third, opens Fly's pricing page first, reads "require a credit card on file" and nearly
  concludes a card is needed to sign up, then opens the free-trial page and finds the fuller
  answer: no card to start, a trial of 2 hours of machine time or 7 days, and a card needed to
  keep going, since adding one ends the trial. Points out that the article's sentence left out
  both the length and the card, though its FAQ mentions the card, so reading one sentence of a
  source is not reading the source. Says each time what kind of page settled it (a
  free-plan docs page, a pricing page, billing docs) and whether it carried a date. For the
  learner's claim, asks only "where would Railway say that?" if they stall. On the prompt
  sentence, asks whether an agent could follow it (a link to the vendor's own page for each
  claim, and the date the agent's information is from, are both things it can give).
- **done when:** the learner has checked the fourth claim on Railway's own docs and found both
  ways it is stale (one-time, not monthly; a free plan after it), can say why the
  article and the blog post don't settle a claim and the vendor's page does, and has written a
  prompt sentence asking for the vendor's own page for each claim. No `checks`: the tutor worked
  three of the four.
- **offer as:** watch it done first: the tutor checks three claims from a vendor-written article
  live, with the false starts left in, then hands you the fourth. The only candidate where you see
  where a check goes wrong (a blog in place of the vendor, a card rule split across a vendor's
  pricing and trial pages), and the claim you check yourself turns out to be stale. Needs a browser and a live session, 25 to 30 minutes.
  `a-check-2025-guide-claims` is all yours from the start.

### `a-check-2025-guide-claims`

- **serves:** `c-check-vendor-claims`
- **supports:** deepen
- **artifact:** `tasks/check-2025-guide-claims.md`, written for this topic: six sentences quoted
  exactly from the deployment guide given to students in this course's 2025 predecessor (SI 211),
  about PlanetScale, Neon, Supabase and Render. The key, checked against those vendors' own pages
  on 2026-10-01, is in its own file, `tasks/check-2025-guide-claims-key.md`, for the tutor only.
  One claim names a free tier since withdrawn (PlanetScale's free MySQL, whose plan ended in 2024).
  The rest hold, with something left out: Render's Postgres "only free for the first month" was
  already the 30-day rule when written (Render's changelog dates it to May 2024) but hides that the
  database is deleted with its data after a 14-day grace period; the others leave out sleep,
  pausing, or the card. None is a limit that has changed since 2025; that case is in
  `a-watch-claims-checked` (Railway's trial) and in `a-plan-claim-checks`'s generator. The guide itself is in the instructor's files and is not available to students, which is
  why its sentences are quoted. 30 to 40 minutes with a browser.
- **learner does:** for each claim, says first which page on the vendor's own site they expect to
  settle it and why; then finds it, copies the sentence that settles it with its address and any
  date; says whether the claim holds, has changed, or is gone; and says what the claim leaves out
  that they would want before signing up. Then says which kind of page settled the most, and which
  claims the vendor's pages couldn't settle.
- **tutor role:** critic
- **tutor does:** before the session, opens every address in the key and confirms it still says
  what is quoted; where it doesn't, the page wins and the tutor updates its own copy of the
  verdict for the session. Shows the task file, never the key file. Takes all six before
  commenting. On any
  verdict resting on something other than the vendor's page (a search result's snippet, a
  comparison article, the agent), asks where the vendor itself says that. Makes sure `g1` is
  discussed: an absence on a pricing page is evidence only once you're sure it's the page that
  would list the plan. Makes sure `g5` is discussed: "free for a month" and "deleted after a month
  unless you pay" are different risks. Ends by asking what the learner would add to a prompt so an
  agent's answer comes with what they'd need to check it.
- **done when:** every claim has a verdict resting on a quoted sentence from the vendor's own
  page, or an honest "the vendor's pages don't settle this"; the learner caught that `g1` is gone
  and that `g5` hides the deletion; and they can say which kind of page settled what. No `checks`:
  the claims were chosen and set out one by one for them with a procedure to follow for each, and
  the learner's prompt sentence comes at the end with the tutor asking for it.
- **offer as:** real claims, from a real guide given to students in this course a year ago, which
  was right when it was written. You do the checking from the start, on real vendor pages, 30 to
  40 minutes. The most hands-on of the study routes, and the one that shows how fast this goes
  stale. Pick `a-watch-claims-checked` to see it done first.

### `a-sort-claim-sources`

- **serves:** `c-check-vendor-claims`
- **supports:** deepen
- **artifact:** no external source beyond the pages named here, all checked as resolving on
  2026-10-01. One claim, which the tutor states: "Render's free web services sleep after 15
  minutes and its free Postgres is free for good." Nine sources to sort:
  1. Render's docs, "Deploy for Free", https://render.com/docs/free.
  2. Render's pricing page, https://render.com/pricing.
  3. The coding agent's own answer, asked "are you sure?".
  4. The Odin Project's Deployment lesson (read in orientation), Render paragraph.
  5. Hatchable, "Free web hosting in 2026" (a vendor's article about other vendors).
  6. Flavio Copes, "Every hosting provider's free tier, side by side", data checked 2026-09-16,
     with disclosed affiliate links.
  7. A 2024 thread on Render's own community forum, which used to be at community.render.com.
     That address now redirects to https://render.com/docs/community, which says "The community
     forum was sunset on March 24, 2026" (the community moved to Discord). A tutor fact, to bring
     in after the learner has sorted it.
  8. A classmate who signed up for Render last week.
  9. Render's MCP server docs, https://render.com/docs/mcp-server.
  20 minutes, with a browser for the last step only.
- **learner does:** sorts the nine, without opening any, into: settles the claim today; useful
  for knowing what to look for, but doesn't settle it; doesn't help with this claim. Says the rule
  they sorted by. Then opens whichever source they put first and checks both halves of the claim
  on it. Then writes what they would add to a prompt so that every claim in an agent's next answer
  comes with the source they put in the first pile.
- **tutor role:** socratic questioner
- **tutor does:** takes the whole sort and the rule before commenting. Asks near-miss questions
  rather than verdicts: on 2, "does the pricing page say what happens when the service is idle,
  or when the database is a month old?" (if it doesn't, the docs page is the one that settles
  it); on 7,
  "it's on Render's site; is it Render saying it?", and afterwards, that the forum has since been
  shut and its threads are stranded at the date they were written; on 9, "it's Render's own page; is it about
  this claim?" (it isn't; it matters for whether an agent can reach the host, which belongs to
  weighing plans); on 4 and 6, "when were these true?"; on 3, the criterion's own line: asking the
  agent whether it's sure does not count. When the learner checks the claim on source 1, makes sure
  they find that the free Postgres expires after 30 days, so the second half of the claim is false.
  On the prompt sentence, asks whether it would make the agent link the vendor's own page rather
  than a comparison article.
- **done when:** the learner's rule puts in the first pile only the vendor's own current pages
  that address this claim (source 1 alone; Render's pricing page has no spin-down or Postgres-expiry wording), says why each of the others doesn't settle it, they found the 30-day expiry on
  Render's docs, and their prompt sentence asks for the vendor's own page per claim. No `checks`:
  the sources were gathered for them and the claim is a single one.
- **offer as:** the quickest route, 20 minutes, mostly without a browser: about what counts as a
  source rather than how to find one. The only candidate that puts the near-misses side by side (a
  forum on the vendor's own site, a careful dated comparison with affiliate links, the vendor's
  docs about something else). Pick `a-check-2025-guide-claims` to do the finding yourself.

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

### `a-study-hatchable-traps`

- **serves:** `c-weigh-hosting-plans`
- **supports:** deepen
- **artifact:** Hatchable, "Free web hosting in 2026",
  https://hatchable.com/articles/state-of-free-web-hosting-in-2026 (updated 2026-08-21, no author
  named; checked 2026-10-01). About 2,800 words in all (the page says "13 min read"). Read only: Why this is confusing in 2026
  (about 145 words); Free database and backend hosting, specifically, with its three subsections
  Free database hosting: managed Postgres and friends, Free backend hosting: somewhere to run
  server code, and Where Hatchable fits (about 815 words together); The traps to watch for (about
  195); What I'd actually recommend by project type (about 185, a bulleted list); How Hatchable
  fits in this map (about 155); and two answers from the FAQ, Is free hosting safe for a real
  business site? (about 75) and Do I need to provide a credit card for free hosting? (about 85).
  About 1,650 words: 13 to 14 minutes of reading in a 45-minute session. Skip the opening map of
  static, app and big-cloud hosting and the rest of the FAQ. What it gives: a list of traps (a
  free trial dressed up as a free tier, 12-month free tiers that start billing, cold starts on free
  app hosting, free-with-ads subdomains, free-for-personal-use-only, unused free machines
  reclaimed: six in all); the advice "Export
  your own dumps." (managed Postgres subsection) and, in the FAQ, "The protection is making sure
  your code and data are exportable."; and the "three accounts" problem, that with a separate
  free database "the 'free' total is three or four accounts with three or four sets of limits"
  (end of the managed Postgres subsection), which Where Hatchable fits says Hatchable "collapses".
  **Warn the learner before they start: the article is written by a hosting vendor, and it
  recommends itself.** Its list puts Hatchable against "Small app with a database", and Where
  Hatchable fits says only that it "is not a Python or Docker host and does not run long-lived
  processes". Hatchable's own developer docs say much more. "Rules & restrictions",
  https://hatchable.com/docs/developers/restrictions (checked 2026-10-01), says "The runtime is a
  sandbox, not Node": "Your handlers run in a locked-down JavaScript sandbox"; "No `npm install`.
  Dependencies are never installed."; "No filesystem writes"; "No build step. No TypeScript
  compile, no JSX transform, no bundler."; each run has a hard cap of 30 seconds of CPU time; and
  the deploy rejects `vite`, `react` and `react-dom` as build-tool dependencies and `pg` and other
  database clients in favor of its own `db.query`. The page doesn't name Express, but Express is an
  npm package that runs as a Node server listening for requests, so none of it runs there. A Problem
  Set 2 app would have its backend rewritten as Hatchable handlers, its Vite build replaced by
  Hatchable's own pattern for React, and SQLite swapped for Hatchable's Postgres: a port, not a
  deploy, and code written for one vendor's SDK, which is deep lock-in. Its dated claims (Render's Postgres expiry, Neon and Supabase signing up without a card,
  Fly.io trial-only) were right on 2026-10-01 as far as each vendor's own page settles them, but
  are claims to check, not facts to carry (`a-watch-claims-checked` uses them that way).
- **learner does:** before reading, writes the five things the goal asks them to compare (sleep;
  what happens past a limit; card required, and what a card on file risks; whether their agent can
  reach the host; how hard it is to move). Reads the assigned sections, and for each trap writes
  which of the five it is about, or that it is about none of them. Then: finds the sentence in Where
  Hatchable fits that shows the list's recommendation can't be taken as given for their app, says
  why, and then, with the tutor, opens Hatchable's restrictions page and says what their app would
  have to become to run there and which of the five that is about; for their own
  Problem Set 2 app on a three-vendor free plan, lists the accounts, the secrets that would have to
  be copied between vendors, and the places they would look when it broke; and notes which of the
  five things the article says nothing about.
- **tutor role:** socratic questioner
- **tutor does:** gives the vendor warning before the reading. Stays out until the learner has the
  traps mapped. Asks near-miss questions: "a 12-month free tier that starts billing; is that about
  a limit, or about a card?" (both: it bills the card it already has); "cold starts: is that the
  same as the app being switched off?" If the learner hasn't found the long-lived-processes
  sentence, asks what the learner's Express server does between requests. On the restrictions
  page, asks what "not Node" and "No `npm install`" mean for a server that is Express, and lets
  the learner arrive at "rewrite it", then asks how hard that code would be to move back off
  Hatchable (lock-in, the fifth of the five). On the three-accounts list, asks what the server
  needs to know to reach the database, and where that comes from. Points out at the end that the
  article mentions an AI "connected over MCP" only as the thing that writes the code, and says
  nothing about an agent reading a host's logs or changing its settings: that is the item the
  learner has to find in vendor docs (a command-line tool, an MCP server or an API), which
  `a-judge-plan-weighings` and the checks supply in the terms.
- **done when:** every trap is mapped to one of the five or to none; the learner has quoted the
  long-lived-processes sentence and, from the restrictions page, said that their app would need
  its backend rewritten and its database swapped to run on Hatchable, and that this is lock-in;
  their three-account list names at least the database connection string going to the server
  host and three places to look; and they noted that the article says nothing about an agent
  reading logs or changing settings. No `checks`: the article did the comparing.
- **offer as:** a real, current, readable survey (updated August 2026) of what free hosting
  costs you, and a lesson in reading one written by an interested party: the vendor's own list
  recommends it for a kind of app its own docs show your app would have to be rewritten to
  become. About 1,650 words plus one docs page, 45 minutes, nothing to run.

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
     method Render disables new builds instead. Free Postgres: "Free Render Postgres databases
     expire 30 days after creation", with a 14-day grace period before Render deletes it.
  25 to 30 minutes.
- **learner does:** reads the story. Before opening Render's page, writes predictions for their
  own app on Render's free plan in four cases: nobody visits for an hour, then a grader does; the
  app is shared on a busy forum and its traffic goes far past the free bandwidth; the same, with a
  card on the account; the database is 35 days old. For each, says whether the app sleeps, stops,
  keeps running, or costs money, and how sure they are. Then reads Render's page and marks each
  prediction right or wrong, quoting the sentence that settles it. Ends by writing, in two
  sentences, what having a card on file risks, and how they would find out the same thing for any
  other vendor.
- **tutor role:** socratic questioner
- **tutor does:** gives the "this is history" framing first. Insists the four predictions are
  written before Render's page is opened. On each wrong prediction, asks what the learner had
  assumed rather than correcting it. On the card case, asks what the difference between the two
  forum cases came down to (only whether a card was on file). Asks whether the story would happen
  on Netlify's free plan today, and where Netlify says so. Does not get into keeping the data in
  the database safe; the expiry case is about the plan's terms, not about backups.
- **done when:** four predictions were recorded before the reveal and each is marked with a quoted
  sentence; the learner can say that a card on file turns a stop into a bill on Render's terms;
  and their last sentence says the answer is in each vendor's own docs on its limits. No `checks`:
  one vendor's terms were laid out for them.
- **offer as:** the vivid one: a real $104,500 bill (since waived, and no longer possible on that
  plan) and then a real vendor's terms, where you predict before you read. About one vendor and
  about what happens past a limit and with a card, more than about choosing. 25 to 30 minutes.
  Pick `a-judge-plan-weighings` for a whole comparison.

### `a-judge-plan-weighings`

- **serves:** `c-weigh-hosting-plans`
- **supports:** deepen
- **artifact:** `tasks/judge-plan-weighings.md`, written for this topic: a class-project app with a
  React frontend, an Express server and a Postgres database; two plans (one vendor for all three,
  and a vendor for each part); four made-up vendors' free-tier terms modeled on terms real vendors
  offered on 2026-10-01, each covering sleep, what happens past a limit, card, agent access (a
  command-line tool, an MCP server, what it can and can't do) and moving; eight students' choices;
  and a key, in its own file for the tutor only (`tasks/judge-plan-weighings-key.md`), that splits
  the differences into those a complete answer must name for this app and those present in the
  terms but not deciding for twenty users. Two choices meet the criterion, for opposite plans. The
  other six miss in different ways: claims the terms don't support, no case for the other plan,
  nothing on the extra vendors, a card treated as a requirement rather than a risk, workarounds
  the terms say nothing about. 25 minutes. Nothing to run.
- **learner does:** reads the app, the plans and the terms. For each of the eight choices, says
  which of the criterion's parts it misses: a difference that matters, the cost of the extra
  vendors, a claim the terms don't support, the case for the other plan. Then writes the list of
  differences a complete answer would name.
- **tutor role:** critic
- **tutor does:** shows the task file, never the key file. Takes all eight verdicts and the list
  before commenting. On the list, sorts the learner's items into the key's two groups and asks why
  each item in the second group doesn't decide anything for twenty users. On each verdict that disagrees with the key, asks the learner to point to the line in
  the terms that supports, or doesn't support, what the student said. Makes sure `v1` against `v2`
  is discussed (opposite choices, both complete), and `v6` (a card that can be billed, not one that
  is required). Checks the learner's list for agent access and for the secrets that have to be
  copied between vendors, the two items students most often leave out.
- **done when:** the learner's verdicts on `v1`, `v2`, `v3`, `v5` and `v6` match the key, and their
  list covers the key's must-name group: sleep, the database expiry, whether a card is required
  and what one on file risks, agent access, moving, and the accounts, secrets and log places the
  extra vendors add. No `checks`: judging other people's choices is not
  making one, and the terms were laid out for comparison.
- **offer as:** the whole comparison in one sitting: the only study route that covers all five
  differences, the extra vendors, and the case for the other plan, including agent access, which
  no reading in this topic covers. Made-up vendors, so nothing here goes stale. 25 minutes, nothing
  to run.

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
  `a-weigh-described-plans/<twist>`.
- **done when:** criterion met with no help, on a Medium or Hard instance.
- **kind:** generator
- **generator:** fixed: the app is a class project with a React frontend, an Express server and a
  Postgres database (described as switched from SQLite so the database can have a host of its
  own), used by about twenty people, built by someone working through a coding agent. Plan one
  puts all three parts with one vendor; plan two uses a different vendor for each part. Vendors are
  made up. Harbor, Brightpage, Kettle and Ledger from `tasks/judge-plan-weighings.md`, with the
  terms given there, are for the worked example only, since `v1` and `v2` already weigh them in
  full. A counting instance invents new vendors on the same pattern, or keeps those names with
  terms changed on at least three of the five dimensions so that the key differs from that
  file's. Each vendor's terms are four to six bullets, always covering: whether anything
  sleeps and how long it takes to wake; what happens past each limit (paused, suspended, writes
  refused, billed with a card, expired and deleted); whether a card is required, and what a card on
  file allows the vendor to bill; agent access (whether there is an official command-line tool, an
  MCP server or an API, and what it can and can't do: deploy, set environment variables, read
  logs, run SQL); and moving (standard tools and exports, or something vendor-specific). What
  varies: the terms, and the twist:
  - `lopsided` (Easy): one plan is better on four of the five, and the strongest case for the
    other is still real.
  - `balanced` (Medium): each plan wins on at least two of the five.
  - `agent-gap` (Medium): the single vendor's agent tool can't read one part's logs, or one split
    vendor has no command-line tool or MCP server at all, only a dashboard.
  - `card-trap` (Hard): every vendor signs up without a card, but one bills overages once a card is
    added (for example, after the learner adds one to unlock a feature); or one asks for a card
    only to verify identity and can't bill it. A pass has to tell these apart.
  - `irrelevant-difference` (Hard): one large difference that doesn't matter for twenty users (a
    bandwidth allowance of 100 GB against 1 TB, a region list, team seats); leaning on it as a
    reason counts as naming something the terms don't support for this app.
  Difficulty as marked. An attempt meant to count runs at Medium or Hard. Across visits, serve
  `agent-gap` and `card-trap` at least once each, reading the labels `served.mjs` returns.
- **worked example:** work one instance aloud, either an Easy one or the Harbor, Brightpage,
  Kettle and Ledger terms if the learner hasn't done `a-judge-plan-weighings`, going through the five
  differences one at a
  time and saying for each what the terms say for each plan and whether it matters for twenty
  users, then listing what the extra vendors add, then arguing the other plan's case as hard as
  possible. At the first level of help on a real attempt, ask only "what happens on each plan when
  nobody has visited for an hour?"
- **doesn't show:** the terms are stated plainly in a few bullets each, so a pass doesn't show the
  learner could find them on real vendors' pages, where they are spread over pricing, docs and
  billing pages and agent access is on a page of its own. Vendors are made up, so a pass says
  nothing about real ones. The two plans are always one-vendor against one-per-part, as the
  criterion says, so mixed plans (one vendor for two parts) are not examined. The learner knows a
  check is on.
- **offer as:** the check that's available now: two plans the tutor wrote, 15 to 20 minutes,
  nothing to run, and the tutor picks the twist so the hard cases (a card that can be billed once
  added, an agent that can't see one part's logs) actually come up. `a-weigh-lab-plans` is the same
  capability on two plans from your own lab.

### `a-weigh-lab-plans`

- **serves:** `c-weigh-hosting-plans`
- **supports:** attempt
- **checks:** `c-weigh-hosting-plans`
- **artifact:** no external source. Two plans for the learner's own Problem Set 2 app taken from the
  session 11 lab (their agent's answer and a tablemate's, or one answer's two options), one putting
  every part with a single vendor and one using a vendor per part, with the vendors' free-tier terms
  as the tutor gathers them from the vendors' own pages. 20 minutes, plus the tutor's preparation.
- **verified:** 2026-10-01
- **learner does:** reads the two plans and the terms sheet, then writes alone which plan they would
  choose for Problem Set 3 and why, as in `a-weigh-described-plans`. Hands it to the tutor.
- **tutor role:** none
- **tutor does:** before the attempt, picks two plans from the lab that fit the criterion's shape;
  if none does, builds the second from the first (the single vendor's own three services, or one
  vendor per part from the vendors the lab answers named). For each vendor, reads its own current
  pages and writes a terms sheet in the bullets of `a-weigh-described-plans`'s generator, with the
  address and date of each page; the sheet must include agent access, from the vendor's own docs
  on its command-line tool, MCP server or API (for example, on 2026-10-01: Render's MCP server,
  https://render.com/docs/mcp-server, which can create services, set environment variables, read
  logs and run read-only SQL, but cannot delete resources or change most settings; Neon's MCP
  server and CLI, https://neon.com/docs/ai/neon-mcp-server, which Neon advises using for
  development only; Netlify's MCP server and CLI,
  https://docs.netlify.com/build/build-with-ai/netlify-mcp-server/). Where a vendor's pages don't
  settle a term, writes "not stated by the vendor" rather than guessing. If the app still uses SQLite
  and a plan puts the database with its own vendor, says in the sheet that the agent would have to
  switch it to that vendor's database. Writes the key as in `a-weigh-described-plans`. Waits during
  the attempt, writing down help word for word. Sends the adjudicator the plans, the sheet, the
  key, the answer and the help. Labels the attempt `a-weigh-lab-plans/<single vendor>-vs-<split
  vendors, joined with +>`.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** the material is whatever the lab produced, so nobody sets the difficulty. Hold
  fixed: one single-vendor plan and one plan with a vendor per part; terms from the vendors' own
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
