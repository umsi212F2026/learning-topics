# Activities: deploy pipeline

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

**Made-up vendors.** Every banked or live scenario in this topic hosts its app on two made-up
vendors, Pinecart and Ropewalk, and each name stands for one vendor with the one set of behaviors
below, everywhere in the topic. A scenario never changes these behaviors and never invents another
vendor; the database is "on a database host outside this plan", unnamed. A scenario's setup quotes
the parts of this roster it needs, word for word. The only real hosts in the topic are in the
orientation's reading. Learner-facing text states the task, never the scoring.

- **Pinecart** hosts a built frontend and serves it through its CDN.
  - Linked to a GitHub repository, a branch and a folder, it builds and deploys the frontend on
    every push to that branch. It cannot wait for GitHub checks.
  - Its repository link can be switched off. A deploy then happens only when Pinecart's deploy
    command runs with a Pinecart deploy token, for example as a step in a GitHub Actions workflow.
    Anyone who holds the token can deploy to the site. The deploy command builds the frontend on
    Pinecart from the pushed commit, using the site's settings, then deploys it.
  - Frontend settings are entered on the site's Settings page, which shows when each setting was
    last saved. A build copies their values into the files it produces, which every visitor's
    browser downloads, so a setting changed after a build has no effect until the next build. The
    Rebuild button builds the commit of the site's latest deploy again, using the current
    settings, and deploys it, whether the repository link is on or off.
  - Its CDN keeps a copy of each page for up to 12 hours. The setting "Clear CDN cache on deploy"
    is on for a new site; with it off, a deploy leaves the CDN's copies in place, and the deploy
    list says "CDN cache kept" beside that deploy. The Clear CDN cache button clears it at any time.
    A request for a page whose address differs, even only after a `?`, is fetched fresh from the
    latest deploy.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced or Failed. A Live deploy shows as Replaced once a later deploy goes live, so only one
    deploy is Live at a time. When a deploy fails, the previous one stays live.
- **Ropewalk** runs a long-running backend, such as an Express server.
  - Linked to a GitHub repository, a branch and a folder, it deploys the backend on every push to
    that branch. Its setting "Wait for GitHub checks", off for a new service, makes it deploy a
    commit only once every check on that commit has passed, and skip the commit if one fails. A
    commit with no checks on it is deployed straight away, as if the setting were off.
  - Its auto-deploy can be switched off ("Auto-deploy: off"); the service stays linked to its
    branch.
  - Each service has a deploy hook: a URL that deploys the latest commit on the linked branch when
    a request is sent to it, whether auto-deploy is on or off. Anyone who has the URL can trigger a deploy.
  - Settings (environment variables) entered on the service's Settings page reach the running
    server and never the browser. Saving one restarts the server with the new value.
  - Its deploy list shows each deploy with its commit, its time and its status: Building, Live,
    Replaced, Failed, or Skipped (checks failed). While auto-deploy is on, every push to its linked
    branch appears on the list, including a push that changes only the frontend, so with "Wait for
    GitHub checks" on, a frontend-only commit whose checks fail shows as Skipped (checks failed). A
    Live deploy shows as Replaced once a later deploy goes live, so only one deploy is Live at a
    time. When a deploy fails, the previous one stays live.

## Check notes

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |
| `c-set-up-auto-deploy` | work with an agent to make an app deploy itself on each push, and confirm that it does | Given an agent's plan for making an app's frontend and backend deploy themselves whenever `main` is pushed to GitHub, says what they would change before agreeing to it, and how they would confirm afterwards that it works. It passes when they catch a plan that would put a secret into the repository, such as a value written into the code or a `.env` file that git will commit; catch a plan that puts a secret into a frontend setting, which the build copies into files every visitor's browser downloads; go along with a plan that keeps secrets in the backend host's settings and keeps a local `.env` file that `.gitignore` covers; for a plan that deploys through GitHub Actions, put the host's deploy token in the repository's GitHub secrets rather than in the workflow file; catch a plan whose deploy doesn't wait for the app's tests to pass, including one that runs them in GitHub Actions while the host deploys every push on its own, and ask for the deploy to wait; and would confirm the pipeline by pushing a small change that shows in the live app only once both the frontend and the backend have deployed it, such as new text the page gets from the backend, and seeing it there, not by taking the agent's word or the host's "deployed" message for it; and by pushing a change with a failing test and seeing that neither part deploys it. Cases: `secret-in-repo`, `frontend-secret`, `sound-plan`, `deploy-token`, `no-test-gate`, `confirm-live`, `confirm-gate`. |
| `c-find-missing-change` | find out why a change doesn't show up in the live app | Given an app that deploys itself from `main` and a change that the live app doesn't show, says what they would look at first (git's output, the commit's checks on GitHub, the host's list of deploys, or the page in the browser), is shown it, and goes on until they can say why and what to do next. It passes when they name the right reason: the change never reached `main` on GitHub (not committed, not pushed, pushed to another branch, or waiting in a pull request nobody has merged), so get it there; the tests failed, so the host never deployed it, and the tests have to pass first; the deploy failed and the old version is still live, so look at that deploy; the browser is showing its own old copy, so reload without its cache; or the host's CDN is serving an old copy, so ask for a fresh one by changing the URL, such as adding `?v=2`, to see whether the new version is there, and clear the CDN's cache so that every visitor gets it; or a frontend setting was changed on the host after the last build, so the frontend has to be built again before it takes effect. Finding out why a deploy failed is not part of it. Cases: `not-pushed`, `not-on-main`, `tests-failed`, `deploy-failed`, `browser-cache`, `cdn-cache`, `old-build-setting`. |
| `c-showcase-pr` | get a change into a repository I can't push to, through a pull request | Given a repository they can't push to, such as the class showcase, and a change to make in it, says how the change gets there with their agent's help: copy the repository into their own account, make the change on a branch of that copy, push it, and open a pull request from that branch into the original repository; and, once it is open, says what to do when one of its checks fails. It passes when they put the change in their own copy, not in the original or in their app's repository; open the pull request from their copy's branch into the original, not the other way round; and fix a failing check by pushing to the same branch, not by opening a new pull request. Cases: `where-to-push`, `pr-direction`, `failing-check`. |

## Coverage

<!--
  Derivation convention: an activity whose `serves` is `all` sits on the `o-orientation` row
  only.
-->

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-deploy-pipeline` | |
| `c-set-up-auto-deploy` | `a-judge-pipeline-plan` | Every scenario carries all seven cases. The two confirmations are answered in words here; the session 12 lab is where they are carried out. |
| `c-find-missing-change` | `a-trace-missing-change`, `a-diagnose-from-evidence` | |
| `c-showcase-pr` | `a-route-showcase-change`, `a-critique-pr-attempt` | A sound proposal (`a-route-showcase-change`'s Hard forms) or a `sound` account (`a-critique-pr-attempt`) carries the same case as the faulty ones, so one agreement can pass a case. Treat a case whose only unaided pass came from agreeing as thin, and serve it again in an open or faulty form before calling the goal met. |

---

## Activities

### `a-read-deploy-pipeline`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** three free pages, no account, read in this order as one sitting. All three opened
  2026-10-05.
  1. **Read first:** MDN Web Docs, "Deploying our app" (the last article of the Client-side
     tooling module; last modified Sep 4, 2026),
     https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Client-side_tools/Deployment.
     Read Post development (about 470 words) and Using GitHub Actions for deployment (about 200).
     Skim The build process. Skip Committing changes to GitHub, which is git commands the learner
     already uses. In Testing, read the opening paragraph, skip the Vitest setup, and read from the
     step that adds the test to the workflow to the end of the section ("This will run the test
     before the build step..."). Skip Summary. About 800 words. What it gives: a GitHub Actions
     workflow that builds and deploys the site on every push to `main`; the green check, yellow
     dot and red cross GitHub shows beside a commit; cache busting; and a test step that stops a
     deploy. It deploys to GitHub Pages, which needs no token, so it doesn't show a workflow
     deploying with a host's token.
  2. **Then:** Render docs, "Deploying on Render", https://render.com/docs/deploys. Read
     Automatic deploys and Configuring auto-deploys (about 110 words), and in Manual deploys the
     paragraph on the Deploy Hook URL (about 60). Skip everything else on the page, including
     Integrating with CI. About 170 words. What it gives: a host watching a linked branch and
     redeploying on every push or merge, its three settings (On Commit, After CI Checks Pass,
     Off), and a deploy hook. Render is one real host, chosen because this page lays the options
     out in a few lines; its settings as quoted were checked 2026-10-05.
  3. **Last:** The Odin Project, "Using Git in the Real World" (JavaScript path),
     https://www.theodinproject.com/lessons/javascript-using-git-in-the-real-world. Look at the
     Workflow diagram. Read the opening of Assignment, Initial setup, Sending your pull request,
     and Don't open unnecessary PRs (about 400 words). Skim Ongoing workflow, which is mostly the
     commands for keeping a fork up to date (about 280). Skip Introduction, Lesson overview and
     Commit messages for collaboration. What it gives: the original repository (upstream), your
     own copy of it on GitHub (a fork, origin), your local copy, a feature branch, and a pull
     request "to merge your feature branch into the original upstream repository's main branch".
  About 1,400 words read and a skim: 11 to 13 minutes of reading, about 16 with the three stops, 21
  with the close. Words in place: auto-deploy (MDN's "deployed automatically", Render's automatic
  deploys), push, branch, GitHub Actions, check (the green check and red cross), CI (Render's
  "After CI Checks Pass"), cache and cache busting (MDN), fork and pull request (Odin). Not in
  place: `.env` file, `.gitignore`, build time, branch protection; they have their own supply,
  and glossing any word as it comes up is optional.
- **verified:** 2026-10-05
- **learner does:** reads in order and stops three times, answering before reading on; "I don't
  know yet" is an honest answer.
  1. After MDN: says in their own words what happens, in MDN's example, between `git push` and the
     new version being live, and what the red cross beside a commit would mean.
  2. After Render: names the ways a deploy can be started that they have now met (the host
     watching a branch, a workflow deploying the site, a request to a deploy hook), and says which
     one MDN's example used.
  3. After Odin: sketches the three repositories (the original, their fork, their local copy) as
     boxes, with an arrow for each push and pull, and one for the pull request.
  Then the close, about 5 minutes, with the reading and the sketch still beside them: answers the
  question the tutor puts: with these pages beside you, could you now attempt these three things
  for real: reading an agent's plan for making your app deploy itself on every push, saying
  what you would change and how you'd confirm it works; working out why a change you made isn't showing in the live app; and
  getting a change into a repository you can't push to, through a pull request?
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you said a deploy hook deploys the code you just wrote; what decides which commit it
  deploys?"). Says that `.env` files, `.gitignore`, build time and branch protection come with the
  words. Does not set or rehearse any question from this topic's checks, and does not say what a
  sound deploy plan contains, where a token belongs, or how to diagnose a missing change; if the
  learner asks, says those are what the session 12 lab and class and the session 13 lab are for,
  and what this topic's other activities check. If the learner stops on a Render setting, says it
  is one real host's settings as of 2026-10-05, and that other hosts name and offer these things
  differently. At the close, puts the readiness question as written above and rules on the
  answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops
  or on whether the tutor thinks they are ready. A plain yes to all three parts is
  `criterion: met`. A hedge on any part, with no plain no, is `criterion: unclear`: go over the
  page that bears on the hedged part once more and put the question again; a second hedge stays
  `unclear`, and the tutor offers an activity on that capability. A plain no to any part is
  `criterion: not met`: record it, ask what is missing, and offer to go back over the stop that
  bears on it, or an activity on it; don't put the question again in the same sitting. This goal
  isn't required, so a no never blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about any of the three capabilities: there is no rehearsal of their questions, by
  design, and the stops are helped and ungraded. MDN deploys to GitHub Pages, so the reading never
  shows a host token or where one is kept, and Render is the only host whose settings the learner
  sees. It shows nothing about the fourteen words, which have their own supply.
- **offer as:** this topic's orientation, one entry holding a sequence: parts of MDN's deployment
  article (a workflow that tests and deploys on each push), a few lines of Render's docs (a host
  that watches the repository, and a deploy hook), then the pull-request half of Odin's
  "Using Git in the Real World", with three short stops and a one-question close. About 20
  minutes.

### `a-judge-pipeline-plan`

- **serves:** `c-set-up-auto-deploy`
- **supports:** attempt
- **checks:** `c-set-up-auto-deploy`
- **artifact:** no external source. A made-up app hosted on Pinecart and Ropewalk, and agents'
  plans for making it deploy itself, from this activity's bank or written live per the generator
  below. Five questions a scenario, about 5 minutes each: 25 to 30 minutes a scenario.
- **verified:** 2026-10-05
- **learner does:** reads the scenario's setup and the one question served. A plan question shows
  one plan an agent proposed and asks whether they would agree to it as it stands, and if not,
  what they would change before agreeing; the fourth plan also asks where the deploy token should
  go. The confirmation question asks how they would make sure the finished pipeline does what it
  should. Answers in two to four sentences.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never says
  how many of a scenario's plans need changing. Gives help whenever it is asked for, and records
  the attempt as helped. At a table in class, one student plays the examiner from the scenario's
  rubric file and the others answer in turn, each in writing before anyone speaks. A remark beyond
  what the question asks is neither credited nor counted against the learner, unless it asks for a
  change that would itself put a secret into the repository or a frontend setting, put the token
  or the deploy hook's URL in the workflow file, or stop a deploy waiting for the tests; such a
  change cancels the credit.
- **done when:** the criterion met with no help. Each question gets one ruling: full credit passes
  every case it carries, and half credit or none passes nothing. A question carrying two cases (a
  `token-in-workflow` plan, the `sound` plan, the confirmation question) is passed only when the
  answer meets both, and its rubric `cases:` line lists both.
- **generator:** a scenario is one app shaped like the course's Problem Set 3 app: a React
  frontend in `client/` and an Express backend in `server/`, in one GitHub repository, each folder
  with tests run by `npm test`, and a database on a host outside the plan. The app varies (a club
  sign-up sheet, a study-group finder, a recipe box, a used-textbook board), and so do its values.
  Fixed: the frontend is on Pinecart and the backend on Ropewalk, quoted from the roster at the
  head of this file; the backend reads the database's connection string, and may read one outside
  service's key, always a service whose key must stay on the server (an AI service, a payment or
  email service, a weather API with a private key), never one whose key is made to sit in the
  browser, such as a maps service; the frontend reads the backend's address. The
  setup names which values are secrets ("Secrets: the database's connection string and the AI
  service's key"), so the question tests the plan and not spotting a secret; the list always
  includes the Pinecart deploy token, and Ropewalk's deploy hook URL whenever a plan in the
  scenario uses the hook. The setup also says
  that the agent proposed each plan in a different session, and that each question is about its
  own plan alone. It also says that neither host is set up yet, so each plan creates the Pinecart
  site and the Ropewalk service; a fault that rests on a roster default for a new service (such as
  "Wait for GitHub checks", off for a new service) rests on that sentence. Only the app's own names are invented per scenario (its environment variable
  names, its config files, the label on the token); the hosts' settings are named word for word
  as the roster names them.

  **A scenario holds five questions, in this order:**
  1. a faulty plan carrying `secret-in-repo`: one of `committed-secret`, `unignored-env` or
     `token-in-workflow`;
  2. a `frontend-secret` plan;
  3. a faulty plan carrying `no-test-gate`: `ungated-watch` or `tests-beside`;
  4. the `sound` plan with the token question, carrying `sound-plan` and `deploy-token`;
  5. the confirmation question, carrying `confirm-live` and `confirm-gate`.
  The faulty plans come first and the `sound` plan after them, since it shows what the others
  should have been; the confirmation question is about the `sound` plan, so it comes last.

  **Plan questions.** One plan, three to six numbered steps in the agent's voice, covering how each
  part gets deployed on a push to `main` and where each value goes. "Would you agree to this plan
  as it stands? If not, say what you would change before agreeing." Every plan has exactly one
  fault, or none: every step not named as the fault below is sound, so a plan with a secret fault
  still waits for the tests, and an ungated plan keeps every secret where it belongs. The fault is
  stated in the plan's words, not hidden by omission, except in the two ungated shapes, where the
  fault is that nothing makes a deploy wait. Every workflow in a plan runs the tests in both
  `client/` and `server/`, and the plan says so ("runs `npm test` in `client/` and in `server/`").
  A faulty step may come with a convenient reason ("so it still works if the setting is
  missing"). In plans 1 to 3, a plan that deploys with the Pinecart deploy token or calls
  Ropewalk's deploy hook leaves where the token or the hook's URL is kept unsaid, except a
  `token-in-workflow` plan, whose fault is the token's place. A learner's remark there about where
  to keep it is neither credited nor counted, unless they say to put it in the workflow file (or
  another committed file), which cancels the credit as `tutor does` says. Shapes, each with the
  case it carries:
  - `committed-secret` (Easy; `secret-in-repo`): a step writes a secret into a source file, such
    as the connection string as a fallback in `server/db.js`, or into a config file that is
    committed.
  - `unignored-env` (Medium; `secret-in-repo`): a step puts the secrets in `server/.env`, and the
    plan's `.gitignore` lists only `node_modules`, or a step says to commit `.env` "so Ropewalk can
    read it".
  - `frontend-secret` (Medium; `frontend-secret`): a step puts a secret into a Pinecart setting so
    the frontend can call the outside service directly.
  - `token-in-workflow` (Medium; `secret-in-repo` and `deploy-token`): Pinecart's repository link
    is off, and a workflow runs the tests and then Pinecart's deploy command; the plan writes the
    Pinecart deploy token into the workflow file, or into a committed file the workflow reads. The
    token is a secret written into a committed file, so it carries `secret-in-repo` in slot 1, and
    one fix (the token into the repository's GitHub secrets) passes both cases.
  - `ungated-watch` (Medium; `no-test-gate`): no workflow and no tests anywhere in the pipeline:
    Pinecart linked to `main` and Ropewalk linked with "Wait for GitHub checks" left off. Neither
    part waits, and that counts as the plan's one fault.
  - `tests-beside` (Hard; `no-test-gate`): a workflow runs `npm test` on every push, worded so it
    sounds like protection ("and CI will check every push"), while Pinecart stays linked to `main`,
    or Ropewalk stays linked with "Wait for GitHub checks" off, so that part deploys whatever the
    tests say.
  - `sound` (Medium; `sound-plan` and `deploy-token`; slot 4 only): secrets only in Ropewalk's
    settings; a local `server/.env` holding them for the learner's own machine, with `.gitignore`
    listing `.env`; only the backend's address in a Pinecart setting; Ropewalk linked with "Wait
    for GitHub checks" on (or its auto-deploy off and the workflow sending a request to the deploy
    hook once the tests pass, the hook's URL's place unsaid); Pinecart's link off and the workflow
    deploying the frontend once the tests pass. The plan ends with the agent's message: "I'll need
    a Pinecart deploy token for the workflow. Where should I keep it?" The token's place is a
    question about the plan, not a fault in it, so the plan still has no fault. Asks: "Would you
    go along with this plan? And what would you tell the agent about where to keep the token?"

  **Confirmation question** (Hard; `confirm-live` and `confirm-gate`), about the scenario's
  `sound` plan, which the question's setup says the agent has carried out ("Suppose the agent has
  carried out plan 4, keeping the token in the repository's GitHub secrets, says everything is set up, and both
  hosts' deploy lists show the latest deploy as Live"). Asks: "How would you make sure that a
  push to `main` now reaches the live app, both its frontend and its backend, and that a push
  whose tests fail goes live in neither?"

  Credit. Plan questions on a faulty plan: full for naming the faulty step and asking for a change
  that removes it (a reason is welcome, not required): the secret into Ropewalk's
  settings or a `.env` that `.gitignore` covers; the outside service called through the backend,
  with the key in Ropewalk's settings; the token in the repository's GitHub secrets; the deploy
  made to wait, by any means the roster allows (Ropewalk's "Wait for GitHub checks", or Pinecart's
  link off and the workflow deploying after the tests). Naming the means is welcome, not required.
  Half for naming the right step with no workable change, or a change that is vague ("keep it
  safe"). None for agreeing, or for objecting only to sound steps. On an `ungated-watch` plan, full
  needs both the tests run somewhere (a workflow running `npm test`) and both parts made to wait
  for them; as on every plan question, saying how each part is made to wait is not required, so
  "run the tests, and make both deploys wait for them" is full. Making only one part wait, naming
  for a part a way of waiting the roster rules out (Pinecart waiting for GitHub checks), or
  turning on "Wait for GitHub checks" with no tests running (a commit with no checks deploys
  straight away), is half. On a `tests-beside` plan,
  asking only for tests to be added, as if none ran, is none. On a `token-in-workflow` plan, the
  credit above goes to both its cases alike. The `sound` plan and the confirmation question each
  carry two cases and get one ruling: full only when the answer meets what each case below asks for
  full, half when it meets at least half on each but not full on both, and none otherwise; their
  rubric `cases:` line lists both. On the `sound` plan, what `sound-plan` asks for: agreeing, with
  or without harmless remarks; it is missed by asking to change a sound step into a faulty one, or
  by refusing the plan on a wrong ground (such as "the `.env` file shouldn't exist at all"). In the
  hook form, the roster's deploy hook deploys the latest commit on the linked branch, not the
  commit whose tests just passed, so a push with failing tests that lands before the earlier push's
  workflow calls the hook can go live untested. A learner who raises this race, as a remark or as
  their reason to qualify or refuse the plan, meets `sound-plan` in full; it is never a wrong
  ground. The question's single ruling still needs `deploy-token` met as well. For the tutor: this
  is a real flaw in the hook form, not a misreading, and a learner who finds it deserves praise for
  it. What `deploy-token` asks for: the repository's GitHub secrets (Actions secrets), read by the workflow,
  for full; "somewhere secret, not in the file" with no place named is half; the workflow file, a
  `.env` file, a Pinecart setting, or the chat is none. So a wrong place for the token fails the
  question however the plan itself is judged. On the confirmation question, an answer may cover the
  two cases in either order. `confirm-live`: full for pushing a small change
  that shows in the live app only once both parts have deployed it (such as new text the page gets
  from the backend, or a frontend change together with the backend change it relies on) and seeing
  it in the live app in the browser; half for a change that shows once only one part has deployed
  it (a frontend-only change, or a backend change checked only by calling the backend directly),
  for pushing a change and checking only the deploy lists or the agent's report, or for opening
  the live app without pushing anything new; none for taking the agent's word or the Live status.
  `confirm-gate`: full for pushing a change that makes a test fail and seeing that neither part
  deploys it, then fixing or reverting it. Either kind of evidence is full: the live app, when the
  push carries something visible from each part (such as new text in the page itself and new text
  the page gets from the backend) and the live app shows neither; or the deploy lists, when
  Ropewalk's list shows the commit Skipped (checks failed), or no Ropewalk deploy of it, and
  Pinecart's list shows no new deploy. The rule against trusting the hosts' word belongs to
  `confirm-live` alone. Half for seeing it for one part only (a failing push whose visible change
  comes from one part only, or checking one host's deploy list), or for watching only the red
  check; none for reading the hosts' settings or asking the agent.

  Every scenario carries all seven cases. **Rotation across the bank:** slot 1 rotates through
  `committed-secret`, `unignored-env` and `token-in-workflow`; slot 3 rotates through
  `ungated-watch`, `tests-beside` with Pinecart linked to `main`, and `tests-beside` with
  Ropewalk's "Wait for GitHub checks" off; slot 4 alternates between Ropewalk waiting for checks
  and Ropewalk deployed through its hook. Scenarios take the next shape in each rotation, so a
  bank of three scenarios shows every shape once, and no two scenarios in a row repeat a slot's
  shape.
- **worked example:** shown only as help when asked for. For a plan: the tutor works a different
  made-up plan aloud, step by step, asking of each value "where does this end up, and who can read
  it there?" and of each deploy "what starts it, and does anything make it wait for the tests?".
  For a confirmation question: the tutor names one thing that would be true of a working pipeline
  and asks the learner what they could see with their own eyes that shows it. MDN's "Deploying our
  app", Testing section, shows a test step placed before a deploy in a workflow, and may be cited.
- **doesn't show:** the learner reads one plan at a time, told to look for changes, and each plan
  has at most one fault, so a pass doesn't show they would catch two faults in one plan, or notice
  one in the middle of a lab while the agent is working. The setup names the secrets, so this
  doesn't show they would recognize one (`deploy-config`'s `c-spot-secret` covers that). Vendors
  are made up, with their behavior stated, so a pass says nothing about reading a real host's
  docs to learn whether it can wait for checks. The confirmation questions are answered in words:
  they don't show the learner carrying the confirmation out. No activity in this topic does; the
  session 12 lab is where the two confirmations are carried out on the learner's own app.
- **offer as:** invented plans for one app, five questions one at a time, about 25 to 30 minutes
  for a scenario, nothing to run; works the same alone with the tutor or at a table in class.
- **note:** On an `ungated-watch` plan, the credit rules don't cover an answer that asks only for the tests to be run (a workflow running `npm test`) with nothing made to wait for them. Rule it half: it supplies one of the two things full credit needs, as turning on "Wait for GitHub checks" with no tests running supplies the other. It is the same misunderstanding `tests-beside` is built to catch.

### `a-review-own-pipeline-plan`

- **was:** a check on `c-set-up-auto-deploy`: the learner judged the plan their own agent wrote
  for making their Problem Set 3 app deploy itself, before it ran, then carried out the two
  confirmations on the live app.
- **status:** dropped (curator, 2026-10-07): a capable agent's own plan usually has no fault, so
  the learner mostly agreed to it and learned little. `a-judge-pipeline-plan` carries every case;
  the session 12 lab is where the confirmations are carried out.

### `a-trace-missing-change`

- **serves:** `c-find-missing-change`
- **supports:** attempt
- **checks:** `c-find-missing-change`
- **artifact:** no external source. A made-up app that deploys itself from `main`, a change it
  doesn't show, and what each place would show, from this activity's bank or written live per the
  generator below. About 5 minutes a scenario.
- **verified:** 2026-10-05
- **learner does:** reads the setup, says where they would look first (git's output on their
  machine, the commit's checks on GitHub, a host's deploy list, or the page in the browser), is
  shown what that place shows, and goes on choosing places until they can say why the change isn't
  showing and what to do next.
- **tutor role:** examiner
- **tutor does:** reveals one place at a time, only the one asked for, reading the rubric's
  evidence for it word for word. For the browser, shows a normal load unless the learner asks for
  a particular view (a reload that skips the browser's cache, a private window or another device,
  or the URL with `?v=2` added). If asked for something the rubric doesn't hold, says "nothing there
  bears on this". Gives no hint about which place to try next, and records the order the learner
  chose. Gives help when asked, and records the attempt as helped. At a table in class, one student
  holds the scenario's rubric file and reveals; the others take turns choosing where to look.
- **done when:** the criterion met with no help: full credit.
- **generator:** a scenario is one app shaped like Problem Set 3's (React frontend on Pinecart,
  Express backend on Ropewalk, one GitHub repository), with the pipeline's setup stated in two or
  three sentences in roster terms (which part is linked to `main`, whether Ropewalk waits for
  checks or has its auto-deploy off and is deployed by the workflow through its deploy hook,
  whether a workflow runs the tests and deploys the frontend). The setup also quotes, word
  for word, the parts of the roster at the head of this file that the scenario needs: for Pinecart,
  always the Settings and build bullet, the CDN bullet and the deploy-list bullet, plus the link
  bullet or bullets that describe how this pipeline deploys the frontend; for Ropewalk, always its
  link and wait bullet and its deploy-list bullet, since its deploy list is always evidence and
  lists every push, frontend-only ones included, plus its auto-deploy and deploy-hook bullets when
  the workflow deploys it through the hook. Then what the learner changed and roughly
  when, a visible change ("the sign-up button now says Join the club", or a frontend setting saved
  on Pinecart's Settings page), and that the live app doesn't show it. The setup never says whether
  anything was rebuilt after a setting was saved; Pinecart's deploy times against the setting's
  save time carry that. One question: "Where would you look first: git's output on
  your machine, the commit's checks on GitHub, a host's deploy list, or the page in the browser?
  You'll be shown what it shows. Keep going until you can say why the change isn't showing and
  what you'd do next." The rubric holds, before the key, the evidence for every place, consistent
  with one cause: `git status`, `git branch --show-current` and `git log --oneline -3` output; the
  latest commits on `main` on GitHub, any open pull request, and the checks on the relevant
  commit; each host's last two or three deploys from its deploy list, with statuses as the
  roster gives them (only one deploy Live, an earlier one that went live shown Replaced, and the
  Live one staying the previous deploy when a later one failed or was skipped, and Ropewalk's list
  holding every push to `main` while its auto-deploy is on, even one that changes only the
  frontend), and beside Pinecart's,
  its Settings page with when each setting was last saved (shown when the learner asks for
  Pinecart's deploy list); and the page under each browser view. True red herrings are allowed
  (an older failed deploy, a failed check on an older commit), false ones are not. Shapes, each
  carrying one case:
  - `uncommitted` (Easy; `not-pushed`): `git status` shows the file modified.
  - `unpushed` (Easy; `not-pushed`): committed; `git status` says the branch is ahead of
    `origin/main` by one commit.
  - `other-branch` (Medium; `not-on-main`): pushed to a branch other than `main`.
  - `unmerged-pr` (Medium; `not-on-main`): in an open pull request nobody has merged.
  - `red-check` (Easy; `tests-failed`): the commit's check failed, and the deploy that waits on it
    never ran: no Pinecart deploy for the commit when the workflow deploys the frontend; for
    Ropewalk, its list shows the commit Skipped when "Wait for GitHub checks" is on, even when the
    change touches only the frontend, or holds no
    deploy for it when its auto-deploy is off and the workflow calls its deploy hook after the
    tests pass.
  - `failed-deploy` (Easy; `deploy-failed`): checks passed; the deploy list shows the commit's
    deploy Failed and the previous one Live.
  - `stale-browser` (Medium; `browser-cache`): the deploy is Live; a normal load shows the old
    page; a reload skipping the cache, a private window, another device and `?v=2` all show the new
    one.
  - `stale-cdn` (Hard; `cdn-cache`): the Pinecart deploy is Live, less than 12 hours old, with
    "CDN cache kept"; a normal
    load, a reload skipping the cache, a private window and another device all show the old page;
    `?v=2` shows the new one.
  - `setting-after-build` (Medium; `old-build-setting`): the change was a frontend setting saved on
    Pinecart's Settings page, with no push or Rebuild since; the latest Pinecart deploy is older
    than the save. To keep a setting in the setup from naming this case, some scenarios of other
    shapes mention a Pinecart setting changed earlier that a later deploy has already picked up,
    and some scenarios of the `failed-deploy`, `stale-cdn` and `stale-browser` shapes have the
    change itself be a Pinecart setting followed by a Rebuild, shown only as a Pinecart deploy of
    the same commit timed after the save, whose deploy then fails, leaves the CDN's copy in place,
    or is hidden by the browser's old copy.
  Credit: full for the case's reason and its next step as the criterion gives them: get the commit
  onto `main` (commit and push, push, merge the branch through a pull request, or merge the open
  pull request); make the tests pass and push; look at the failed deploy (finding the cause is not
  asked for); reload without the browser's cache; see the new version with a changed URL such as
  `?v=2` (asked for during the trace, or named in the answer) and clear Pinecart's CDN cache so
  every visitor gets it; rebuild the frontend (the Rebuild button, or a push). Half for the right
  reason with the next step missing or wrong (for `stale-cdn`, clearing the browser's cache, or
  waiting); none for a wrong reason. The order of places chosen is recorded, not credited. Across
  the bank, every shape appears at least once.
- **worked example:** shown only as help when asked for: the tutor traces a different made-up
  scenario aloud, saying at each place what each possible cause would show there and which causes
  the evidence rules out.
- **doesn't show:** the learner is told the four places to look, and each scenario has exactly one
  cause, so a pass doesn't show they would think of these places unprompted, or untangle two
  causes at once. Vendors are made up and their behavior is given, so a pass says nothing about
  finding a real host's deploy list or cache controls.
- **offer as:** the investigation itself, interactive: you choose where to look and are shown what
  you'd see, one place at a time. About 5 minutes; works well at a table with one person holding
  the evidence.

### `a-diagnose-from-evidence`

- **serves:** `c-find-missing-change`
- **supports:** attempt
- **checks:** `c-find-missing-change`
- **artifact:** no external source. A made-up app, a change its live app doesn't show, and
  everything the four places show, all at once, from this activity's bank or written live per the
  generator below. About 2 to 3 minutes a question.
- **verified:** 2026-10-05
- **learner does:** reads the setup and the evidence, then says why the change isn't showing and
  what they would do next.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting. Gives help when
  asked, and records the attempt as helped. At a table in class, each student writes an answer
  before any are read out, and one checks them against the rubric.
- **done when:** the criterion met with no help: full credit.
- **generator:** as `a-trace-missing-change`'s generator, with the same app shape, setup (the
  roster bullets quoted word for word, and nothing said about a Rebuild), shapes, cases and credit,
  except for difficulty and except that the evidence is in the task, shown at once in four labeled
  blocks (git's output, GitHub, the deploy lists, the browser), and the question is "Why isn't the change showing,
  and what would you do next?". The deploy-lists block shows each host's statuses as
  `a-trace-missing-change`'s evidence does (one deploy Live, earlier ones that went live
  Replaced, and on Ropewalk's list every push to `main` while its auto-deploy is on, frontend-only
  ones included), and always holds, beside Pinecart's deploys,
  its Settings page with when each setting was last saved. The browser block always shows a normal load and a reload that
  skips the cache; in half the `stale-cdn` questions it also shows `?v=2`, and in the other half it
  doesn't, so full credit there needs the learner to propose changing the URL as well as clearing
  the CDN's cache. Difficulty is this activity's own, since the evidence is all shown: Easy for
  `uncommitted`, `unpushed`, `red-check`, `failed-deploy` and `stale-browser` (the cache-skipping
  reload in the browser block settles it); Medium for `other-branch`, `unmerged-pr` and
  `setting-after-build`; for `stale-cdn`, Medium when the block shows `?v=2` and Hard when it
  doesn't. Scenarios are not shared with `a-trace-missing-change`'s bank. A scenario may
  hold several questions, each a different change on a different day with its own evidence, in no
  fixed order of cases.
- **worked example:** as `a-trace-missing-change`'s.
- **doesn't show:** the learner never chooses where to look, so this shows nothing about the
  criterion's first step; it shows reading evidence already gathered. The rest of
  `a-trace-missing-change`'s `doesn't show` applies too.
- **offer as:** the quick version: all the evidence on one screen, say what happened. About 2 to 3
  minutes; good for review, or for a learner who wants several in a row.

### `a-route-showcase-change`

- **serves:** `c-showcase-pr`
- **supports:** attempt
- **checks:** `c-showcase-pr`
- **artifact:** no external source. A made-up repository the learner can't push to and a change to
  make in it, from this activity's bank or written live per the generator below. About 2 to 3
  minutes a question.
- **verified:** 2026-10-05
- **learner does:** reads the setup and the one question served, and says in two or three sentences
  where the change goes, which way the pull request runs, or what to do about a failing check.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting. Gives help when
  asked, and records the attempt as helped. At a table in class, one student examines from the
  rubric file while the others answer, each in writing first.
- **done when:** the criterion met with no help, case by case: full credit on a question passes
  its case.
- **generator:** a scenario gives the learner a GitHub username (`mara-codes`), their app's
  repository (`mara-codes/study-buddy`), and a repository owned by someone else that they can read
  but not push to: a made-up class's, club's or group's showcase (`northfield-cs/showcase`,
  `riverside-hack-club/gallery`), never the course's real showcase. It says what the repository
  holds (one file per app in `apps/`, or a list in `apps.json`), the change to make (adding an
  entry for their app), that a check runs on every pull request to it (named, such as
  `validate-entries`), and that their agent will do the typing while they say what should happen.
  Questions, in this order, each carrying one case:
  - `where-to-push` (Medium): "Before any pull request exists, where does your change get made and
    pushed?" Or (Hard) the agent proposes a place ("I'll add the entry to `study-buddy` and push to
    `main`", "I'll push a branch to `northfield-cs/showcase`", or the sound one, "I'll fork the
    showcase into your account and push a branch there") and the question asks "Would you go along
    with this? If not, where should it go?". Full: in their own copy of the repository (a fork,
    under their account), pushed there, on a branch or not; for the sound proposal, agreeing.
    Half: "a new branch" with no repository named. None: the original, or their app's repository.
  - `pr-direction` (Medium): "Your change is pushed. GitHub's page for opening a pull request asks
    for a base repository and branch and a head repository and branch. What do you choose for
    each?" Or (Easy) the same as a four-option multiple choice of base and head pairs, `type: mcq`.
    Or (Hard) the agent reports "I've opened a pull request from `northfield-cs/showcase:main`
    into `mara-codes/showcase:add-study-buddy`", reversed, or the right way round, and the question
    asks whether it is right and, if not, what it should be. A scenario whose report is reversed
    says in its setup that other entries have been merged into the original since the fork, since
    GitHub opens a pull request from the original's `main` into the fork's branch only when that
    `main` has commits the branch lacks. Full: base is the original repository
    and its `main`; head is their fork and the branch with the change (and, for a right-way report,
    agreeing). None: reversed, or their app's repository anywhere.
  - `failing-check` (Medium): "Your pull request is open, and its check has failed with this
    message: ..." (a fault in the learner's own entry, such as a missing field). "What do you do?"
    Or (Hard) the agent proposes "I'll close this pull request and open a fresh one with the fix",
    or, the sound one, "I'll fix the entry on the same branch and push", and the question asks
    whether they would go along. Full: fix the entry on the same branch of their fork and push,
    so the open pull request picks up the commit and the check runs again; for the sound proposal,
    agreeing. Half: "update the pull request" with no word on how. None: a new pull request,
    closing it, or pushing the fix anywhere else.
  A scenario has one question of each kind, in the order above, since a later question names where
  the change went. Across the bank, each kind appears in each of its forms, and each Hard form
  appears both with a sound proposal and with a faulty one.
- **worked example:** shown only as help when asked for. The Odin Project, "Using Git in the Real
  World" (JavaScript path), its Workflow diagram and Sending your pull request; or GitHub Docs,
  "Creating a pull request from a fork",
  https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork,
  for the base and head choice, and "Creating a pull request",
  https://docs.github.com/articles/creating-a-pull-request, which says commits pushed later to the
  same branch are added to the open pull request. Both GitHub pages opened 2026-10-05.
- **doesn't show:** each question carries one step and the setup says the repository can't be
  pushed to, so a pass doesn't show the learner would realize that unprompted, or keep all three
  steps straight in one go with an agent offering shortcuts. Nothing is run, so it doesn't show
  they could find these choices on GitHub's pages.
- **offer as:** the showcase route, one step at a time: where the change goes, which way the pull
  request runs, what to do when a check fails. About 2 to 3 minutes a question.

### `a-critique-pr-attempt`

- **serves:** `c-showcase-pr`
- **supports:** attempt
- **checks:** `c-showcase-pr`
- **artifact:** no external source. A made-up classmate's account, or an agent's summary, of how
  they got an entry into a repository they couldn't push to, from this activity's bank or written
  live per the generator below. About 3 minutes a question.
- **verified:** 2026-10-05
- **learner does:** reads the account, which may or may not have a step that goes wrong, and says
  whether they would have gone along with it, and if not, which step goes wrong and what should
  have happened instead.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never says
  whether an account has a wrong step. Gives help when
  asked, and records the attempt as helped. At a table in class, each student writes the step and
  the fix before any are read out, and one checks them against the rubric.
- **done when:** the criterion met with no help: full credit.
- **generator:** a scenario uses the same kind of setup as `a-route-showcase-change`'s (a username,
  their app's repository, a made-up showcase they can't push to, its check) with different names.
  Each question is one account of four to seven numbered steps, in the first person of a made-up
  classmate or as an agent's summary of what it did, with one step that goes wrong or none, and
  every step before a wrong one sound. "Would you have gone along with this? If a step goes wrong,
  which one, and what should have happened instead?" In `entry-in-app-repo` and `reversed-pr`, the
  account ends at the wrong step or one step after it, and that later step only follows from the
  wrong one (the pull request opened in the app repository). A `new-unrelated-repo` account ends at
  the wrong step, creating the new repository and pushing the entry to it, and never goes on to a
  pull request, since GitHub cannot open one from a repository with no shared history. When a shape needs the check to fail (`new-pr-for-fix`,
  `fix-on-wrong-branch`, or a `sound` account written around `failing-check`), the account never
  shows the entry's contents, so that no step before the failure reads as a fault: the failure
  shows only in the check's message, quoted after the pull request is opened. Shapes, each carrying
  one case:
  - `entry-in-app-repo` (Easy; `where-to-push`): the entry is added to the classmate's own app
    repository, and a pull request is opened there.
  - `new-unrelated-repo` (Medium; `where-to-push`): the account states the lack of push access as a
    fact, not as an attempted step ("I don't have push access to the showcase"), and the agent
    creates a new repository of the classmate's and pushes the change there instead of forking the
    original. No step tries to push to the original, and the account ends with that push.
  - `reversed-pr` (Medium; `pr-direction`): the change is on a branch of the fork, and the pull
    request runs from the original's `main` into that branch. A scenario holding a `reversed-pr`
    account says in its setup that other entries have been merged into the original since the
    fork, since GitHub opens a pull request that way round only when the original's `main` has
    commits the fork's branch lacks.
  - `new-pr-for-fix` (Easy; `failing-check`): the check fails, and the fix goes into a second pull
    request.
  - `fix-on-wrong-branch` (Hard; `failing-check`): the check fails, and the fix is pushed to the
    fork's `main` while the pull request comes from another branch of the fork, so the pull request
    never gets it.
  - `sound` (Medium; the case of the step it is written around): every step sound, the whole route
    from fork to fixed check, with one step (where the change was pushed, which way the pull
    request runs, or how a failing check was fixed) given in full detail; it carries that step's
    case.
  Credit: full for naming the wrong step and what should have happened (fork the original and push
  there; base the original's `main`, head the fork's branch; push the fix to the pull request's own
  branch). Naming the step that follows from the wrong one counts as naming the wrong one when the
  fix given goes back to it (the pull request should come from a fork of the original), and as
  half when the fix stays with the later step (open the pull request somewhere else). Half for the
  right step with a missing or wrong fix. None for agreeing to a faulty account, or for naming a
  sound step. On a `sound` account: full for agreeing; none for naming any step as wrong. In an
  account built around a failing check (`new-pr-for-fix`, `fix-on-wrong-branch`, or a `sound`
  account written around `failing-check`), the step that added the entry really did add it with
  a field missing, which the check later reports. A learner who says so ("step 2's entry was
  missing its `url`") while agreeing to the route, or while naming the route's actual wrong step,
  is saying something true: that remark is harmless, neither credited nor counted against them,
  and is not naming a sound step as wrong. A
  scenario may hold several accounts, with at least one faulty account and at most one `sound`
  one. They are separate accounts of the same classmate's attempt, each judged on its own. Their
  order is fixed, because one account can give another away (an account with a sound fork answers
  one that skips the fork, and one with the right pull-request direction answers one that
  reverses it), so an account comes only after those it could answer: faulty accounts first, in the order of their cases, `where-to-push`, then `pr-direction`,
  then `failing-check`, and the `sound` account, if any, last. Across the bank, every shape appears, and `sound`
  accounts are written around each of the three steps.
- **worked example:** as `a-route-showcase-change`'s.
- **doesn't show:** each account has at most one wrong step, so a pass doesn't show the learner
  would untangle two, and it is a finished account, so it doesn't show they would notice a wrong
  step in their own agent's work as it happens. The rest of `a-route-showcase-change`'s `doesn't show` applies too.
- **offer as:** someone else's whole attempt to judge, which may or may not hold a mistake: more reading, less recall than
  saying the route yourself. About 3 minutes a question.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
