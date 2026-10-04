# Activities: deploy config

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-04. A deliberate deviation from `curation/generate`, which asks for at least one activity
per goal that isn't a check. By the instructor's decision, every activity in this topic sets
questions with rubrics, and there are no study-only activities: practice is an attempt with help,
which is recorded but doesn't count, and a check is an attempt without. The `study` cells in
Coverage are empty for that reason, not because something is missing.

2026-10-04. A second deliberate deviation, from `curation/bank-check`, which asks that no question
give away another's answer in the same scenario. By the instructor's decision, a scenario here is
one story served in file order in study, and a later question may reveal an earlier one's answer.
A quiz or a review draws few questions from any one scenario. Every question names at least one
goal; there are no warm-ups.

2026-10-04. A third deliberate deviation, from the `c-spot-secret` criterion, which asks the
learner to say whether a value is a secret and why. On message questions, by the instructor's
decision, full credit for `c-spot-secret` needs only the call (secret, or public), since the
reason a learner gives there is naturally about the route, not the value. Exchange questions
still ask for and credit the reason.

2026-10-04. A known weakness, waiting on a change to the workflow. `c-spot-secret` and
`c-judge-secret-request` each have two sides (a secret and a public value; a request to decline
and one to go along with), and `c-trace-setting-value` names cases it must include. Under `one
unaided pass`, a pass on any one question meets the goal, so the easiest side can certify it. The
instructor is adding a way for a criterion to name its cases and for the bar to require each; when
it lands, the rubrics here gain `cases:` lines and nothing else changes. Until then, prefer serving
a learner the side they haven't shown.

2026-10-04. One activity, `a-deploy-chat`, serves every capability goal, by the instructor's
choice: one scenario carries questions across all four goals, so there is no choice of activity
to offer, and its `offer as` describes it rather than distinguishing it.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `c-trace-setting-value` | follow an agent's explanation of a setting it wants: what it is for and where its value comes from | Given an app whose frontend, backend and database are each on a named vendor, and an exchange in which an agent asks for a setting under a name the learner hasn't met, a student asks what it is for and where its value comes from, and the agent answers. The learner says what the setting is for and whose value it needs (the frontend's address, the backend's address, the database's connection details, or nobody's, because a host sets it automatically, as with `PORT`). It passes when both are right, including when the setting belongs to one part but holds another part's address, such as the backend's allowed origin holding the frontend's address, and when the agent's answer names only a vendor that hosts two parts. Finding the value on the vendor's site, whether it is a secret, and what to do with one are not part of it. |
| `c-spot-secret` | tell whether a value an agent asks for is a secret | Given a setting an agent asks for and its explanation of what the value is, says whether the value is a secret and why: someone holding it could get into something of yours. It passes when they call a secret one, including one whose name doesn't say so, such as a token or a connection string, and don't call a public value one, such as the frontend's or the backend's address. What to do with a secret is not part of it. |
| `c-judge-secret-request` | tell whether an agent's request would send a secret through the chat or into the code | Given one message from an agent deploying an app, which asks for a value or proposes a step, says whether they would go along with it. It passes when they decline a request that would put a secret in the chat or let the agent write one into a file, and go along with one that wouldn't, including an instruction to put a secret into the host's settings themselves. What to do instead is not part of it. |
| `c-secret-instead` | say what to do instead of handing a secret to the agent, and why | Given a message from an agent that would route a secret through the chat or into a file, says what they would do instead and why. It passes when they say to put the secret into the host's settings themselves and tell the agent it is there, and give both reasons: the chat is kept and can be shared, and an agent holding the secret can write it into a file that gets committed. Dealing with a secret that has already leaked is not part of it. |

## Coverage

<!--
  Derivation convention: an activity carrying `checks` sits only in the `checks` cell, never in
  `study`. No orientation row: goals.md has no orientation goal, because cloud-hosting and
  database-hosting come first and lay the area out. Empty `study` cells are by design; see
  Check notes.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `c-trace-setting-value` | | `a-deploy-chat` | |
| `c-spot-secret` | | `a-deploy-chat` | |
| `c-judge-secret-request` | | `a-deploy-chat` | |
| `c-secret-instead` | | `a-deploy-chat` | |

---

## Activities

### `a-deploy-chat`

- **serves:** `c-trace-setting-value`, `c-spot-secret`, `c-judge-secret-request`, `c-secret-instead`
- **supports:** attempt
- **checks:** `c-trace-setting-value`, `c-spot-secret`, `c-judge-secret-request`, `c-secret-instead`
- **artifact:** no external source. Made-up apps being deployed by an agent, and the agent's side
  of the conversation, from this activity's bank or written live per the generator below. About 2
  to 5 minutes a question.
- **verified:** 2026-10-04
- **learner does:** reads the scenario's setup (the app, and which vendor hosts each part) and the
  one question served, and answers it. An exchange question asks what a setting is for, whose
  value it needs, and whether its value is a secret, and why. A message question asks whether
  they would go along with what the agent asks, and why or why not. A repair question asks for the
  reply they would send the agent, and why that is safer.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never shows
  the rubric or says how many of a scenario's messages are safe. Gives help whenever it is asked
  for, and records the attempt as helped. A remark beyond what the question asks (where to find a
  value on a vendor's site, or what to do instead in answer to a message question) is neither
  credited nor counted against them.
- **done when:** each goal the question names has its criterion met with no help.
- **generator:** a scenario is one app shaped like Problem Set 2 (a React frontend, an Express
  backend and a database) being deployed by an agent. Its setup names the made-up vendor each
  part is on, with that vendor's offer in a line; Brightpage, Kettle, Harbor and Larder may be
  reused, or new vendors invented on the same pattern. The setup never says which values are
  secrets. **A scenario is a story, served in study in file order:** exchange questions first,
  then message questions, then repair questions, so a later question may reveal an earlier one's
  answer but never the reverse. Give a scenario as many questions as its app supports, across all
  three kinds. Setting names are invented, never `PORT`, `VITE_API_URL`, `ALLOWED_ORIGIN` or
  `DATABASE_URL`, and never repeated across scenarios; within a scenario, message and repair
  questions reuse its setting names so the story holds together. Every question names at least
  one goal.

  **Exchange questions.** The agent's request, naming one setting; a student's question, asking
  what it is for and where its value comes from, worded as a student might; and the agent's
  answer, one to three sentences, true to the setup, saying what the value is used for and where
  to copy it from by naming a vendor or a dashboard, never in the words "the frontend's address"
  or "the backend's address". Then: what is it for, whose value does it need (the frontend's
  address, the backend's address, the database's connection details, or nobody's, because a host
  sets it), and is it a secret, and why. Shapes:
  - `plain` (Easy): the name says plainly whose value it holds; not a secret.
  - `host-sets` (Easy): a value the host provides itself, which the agent says not to add.
  - `secret-db` (Medium): the database's connection details, as a connection string or as a
    token or password on its own, under a name that doesn't say "secret", "password" or "key";
    a secret.
  - `cross-part` (Medium): a setting read by one part that holds another part's address: a
    frontend setting named for the frontend that holds the backend's address, or a backend
    setting holding the frontend's address (the pages it accepts requests from).
  - `shared-vendor` (Hard): the setup puts two parts on one vendor (like Harbor), each with its
    own address, and the agent's answer names only the vendor. Neither the setup's example
    addresses nor the setting's name may say which part's value it holds (no `api`, `server`,
    `backend`, `client`, `site` or `frontend` pointing at the answer), unless the name points the
    wrong way, which makes the question also `cross-part`, its hardest form.
  Every exchange question names `c-spot-secret`. Only a `shared-vendor` one also names
  `c-trace-setting-value`: when each part is on its own vendor, the vendor named in the answer
  gives the part away.

  **Message questions.** One message from the agent, which asks for a value or proposes a step,
  then "Would you go along with this? Say why or why not." Shapes:
  - `paste-in-chat` (Easy; routes a secret): asks for a secret to be pasted so the agent can set
    it up.
  - `write-into-code` (Medium; routes a secret): proposes putting a secret in a source file, with
    a convenient reason ("so it works the same everywhere"). The message never also asks for the
    secret in the chat (the agent fetches it some other way), so declining it can't rest on the
    chat alone.
  - `debug-lure` (Hard; routes a secret): asks for the secret indirectly, as a copy or screenshot
    of the page that shows it, or the output of a command that prints it, to "check" something.
  - `public-address` (Easy; routes none): asks for the frontend's or the backend's address.
  - `other-step` (Medium; routes none): a deploy step with no value in it, worded so it sounds
    risky (it mentions the database, the settings page or a redeploy).
  - `dashboard-instruction` (Hard; routes none): tells the learner to add a setting on the host
    and paste the secret there themselves, naming the secret but never asking for it.
  Every message question names `c-judge-secret-request`, credited from the decision. One whose
  message involves a value (every shape but `other-step`) also names `c-spot-secret`, with full
  credit for saying whether the value is a secret, with or without an explanation. Mix messages
  that route a
  secret with ones that don't, in no fixed proportion.

  **Repair questions.** One message in the shape `paste-in-chat`, `write-into-code` or
  `debug-lure`, then "This message would put a secret where it shouldn't go. Write the reply you
  would send the agent, then say why that is safer. There may be more than one reason." Every
  repair question names `c-secret-instead`. A full-credit answer says the learner will put (or has
  put) the secret into the host's settings themselves and tells the agent it is there, and gives
  both reasons: the chat is kept and can be shared, and an agent holding the secret can write it
  into a file that gets committed. Naming the setting or the host is welcome but not required.

  Each scenario has at least one `secret-db` exchange. A scenario meant to bear on
  `c-trace-setting-value` needs a setup with one vendor hosting two parts, and at least two
  `shared-vendor` exchanges, one of them also `cross-part`.
- **worked example:** for an exchange, say what the agent's answer says the value is used for,
  then ask whose address that is or what it unlocks, then whether someone holding it could get
  into something. For a message, say what value would pass through the chat or into a file, and
  whether holding it lets someone into something. For a repair, write a reply aloud in the
  pattern "I've added it in Kettle's settings as `PG_CONNECTION`; use that, and don't put it in
  any file", then say why.
- **doesn't show:** every exchange already holds a good question and a clear, correct answer, so a
  pass doesn't show the learner would ask the question themselves, or could make sense of a vague
  or wrong answer. The learner answers one question at a time, knowing they are being asked to,
  so a pass doesn't show they would notice a risky request in the middle of a deploy; and a
  repair question says the message is unsafe, so it doesn't show they would notice. Vendors are
  made up, so a pass says nothing about real dashboards.
- **offer as:** the agent's side of a deploy, one question at a time, about 2 to 5 minutes each,
  nothing to run: the settings it asks for, the requests it makes, and what you say back.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
