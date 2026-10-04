# Activities: deploy config

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-10-04. A deliberate deviation from `curation/generate`, which asks for at least one activity
per goal that isn't a check. By the instructor's decision, every activity in this topic sets
questions with rubrics, and there are no study-only activities: practice is an attempt with help,
which is recorded but doesn't count, and a check is an attempt without. The `study` cells in
Coverage are empty for that reason, not because something is missing.

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
| `c-trace-setting-value` | | `a-read-described-exchange` | |
| `c-spot-secret` | | `a-read-described-exchange` | |
| `c-judge-secret-request` | | `a-judge-requests` | |
| `c-secret-instead` | | `a-repair-request` | |

---

## Activities

### `a-read-described-exchange`

- **serves:** `c-trace-setting-value`, `c-spot-secret`
- **supports:** attempt
- **checks:** `c-trace-setting-value`, `c-spot-secret`
- **artifact:** no external source. Made-up apps and the exchanges their agent has about settings,
  from this activity's bank or written live per the generator below. About 5 minutes a question.
- **learner does:** reads the scenario's setup (the app, and which vendor hosts each part) and the
  one exchange served, then says what the setting is for, whose value it needs (the frontend's
  address, the backend's address, the database's connection details, or nobody's, because a host
  sets it), and whether its value is a secret, and why.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never shows
  the rubric. Gives help whenever it is asked for, and records the attempt as helped. A remark
  about finding the value on a vendor's site, or about what to do with a secret, is neither
  credited nor counted against them.
- **done when:** each goal the question names has its criterion met with no help.
- **generator:** a scenario is one app shaped like Problem Set 2 (a React frontend, an Express
  backend and a database), with a setup naming the made-up vendor each part is on and that
  vendor's offer in a line. Brightpage, Kettle, Harbor and Larder may be reused, or new vendors
  invented on the same pattern. The setup never says which values are secrets. Each question is
  one exchange: the agent's request, naming one setting; the student's question, asking what it
  is for and where its value comes from, worded as a student might; and the agent's answer, one
  to three sentences, true to the setup, saying what the value is used for and where to copy it
  from by naming a vendor or a dashboard, never in the words "the frontend's address" or "the
  backend's address". Then the question itself: what is it for, whose value does it need, and is
  it a secret, and why. Setting names are invented, never `PORT`, `VITE_API_URL`,
  `ALLOWED_ORIGIN` or `DATABASE_URL`, and never repeated across the bank. Each exchange takes one
  shape:
  - `plain` (Easy): the name says plainly whose value it holds; not a secret.
  - `host-sets` (Easy): a value the host provides itself, which the agent says not to add.
  - `secret-db` (Medium): the database's connection details, as a connection string or as a
    token or password on its own, under a name that doesn't say "secret", "password" or "key";
    a secret.
  - `cross-part` (Medium): a setting read by one part that holds another part's address: a
    frontend setting named for the frontend that holds the backend's address, or a backend
    setting holding the frontend's address (the pages it accepts requests from).
  - `shared-vendor` (Hard): the setup puts two parts on one vendor (like Harbor), each with its
    own address, and the agent's answer names only the vendor. The setup's example addresses
    must not say which part each is for (no `api` in one of them). The hardest form is also
    `cross-part`.
  **Every question names `c-spot-secret`**, since each asks whether a value is a secret, public
  addresses included. **Only a `shared-vendor` question also names `c-trace-setting-value`.**
  When each part is on its own vendor, the vendor named in the agent's answer gives the part away,
  so a pass on any other shape, `cross-part` included, doesn't show the cases the criterion names.
  A scenario has four to six questions, with at least one `secret-db`. A scenario meant to bear
  on `c-trace-setting-value` needs a setup with one vendor hosting two parts, and at least two
  `shared-vendor` questions, one of them also `cross-part`.
- **worked example:** work one Easy exchange aloud: say what the agent's answer says the value is
  used for, then ask whose address that is or what it unlocks, then whether someone holding it
  could get into something.
- **doesn't show:** the exchange already holds a good question and a clear, correct answer, so a
  pass doesn't show the learner would ask the question themselves, or could make sense of a
  vague or wrong answer. Vendors are made up, so a pass says nothing about real dashboards.
- **offer as:** one agent exchange at a time, about 5 minutes, nothing to run: a setting your agent
  asks for while you deploy, and whose value it needs.

### `a-judge-requests`

- **serves:** `c-judge-secret-request`
- **supports:** attempt
- **checks:** `c-judge-secret-request`
- **artifact:** no external source. Made-up apps and messages from the agent deploying them, from
  this activity's bank or written live per the generator below. About 2 minutes a question.
- **learner does:** reads the scenario's setup and the one agent message served, then says whether
  they would go along with it.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never shows
  the rubric. Never says how many of a scenario's messages are safe. Gives help whenever it is
  asked for, and records the attempt as helped. If the learner goes on to say what they would do
  instead, that is welcome but not judged here; it is `a-repair-request`'s.
- **done when:** the question's criterion met with no help.
- **generator:** a scenario is one app shaped like Problem Set 2, with its frontend, backend and
  database on made-up vendors, and a setup that says where the database's connection details are
  shown and that they include its password. Each question is one message from the agent
  deploying the app, which asks for a value or proposes a step, and the question "Would you go
  along with this?". Each message takes one shape:
  - `paste-in-chat` (Easy; routes a secret): asks for a secret to be pasted so the agent can set
    it up.
  - `write-into-code` (Medium; routes a secret): proposes putting a secret in a source file, with
    a convenient reason ("so it works the same everywhere").
  - `debug-lure` (Hard; routes a secret): asks for the secret indirectly, as a copy or screenshot
    of the page that shows it, or the output of a command that prints it, to "check" something.
  - `public-address` (Easy; routes none): asks for the frontend's or the backend's address.
  - `other-step` (Medium; routes none): a deploy step with no secret in it, worded so it sounds
    risky (it mentions the database, the settings page or a redeploy).
  - `dashboard-instruction` (Hard; routes none): tells the learner to add a setting on the host
    and paste the secret there themselves, naming the secret but never asking for it.
  **Medium and Hard questions name `c-judge-secret-request`; Easy ones name no goal** and are
  warm-ups, because a pass on the plainest request shows little. A scenario has five to seven
  questions, mixing messages that route a secret with ones that don't in no fixed proportion.
- **worked example:** work an Easy message aloud: say what value would pass through the chat or
  into a file, and whether holding that value lets someone into something.
- **doesn't show:** the learner judges one message at a time, knowing they are being asked to, so a
  pass doesn't show they would notice such a request in the middle of a deploy. The bar is one
  unaided pass, so a pass on one shape doesn't show the others: declining a `debug-lure` doesn't
  show they would go along with a `dashboard-instruction`.
- **offer as:** one message at a time, about 2 minutes, nothing to run: would you go along with what
  your agent just asked?

### `a-repair-request`

- **serves:** `c-secret-instead`
- **supports:** attempt
- **checks:** `c-secret-instead`
- **artifact:** no external source. Made-up apps and unsafe messages from the agent deploying them,
  from this activity's bank or written live per the generator below. About 5 minutes a question.
- **learner does:** reads the scenario's setup and the one agent message served, which would route
  a secret through the chat or into a file. Writes the reply they would send the agent, then one
  sentence on why.
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting, and never shows
  the rubric. Gives help whenever it is asked for, and records the attempt as helped.
- **done when:** the question's criterion met with no help.
- **generator:** the same kind of scenario as `a-judge-requests`, but never reusing a message from
  that activity's bank, so that neither gives the other away. Each question is one message in the
  shape `paste-in-chat`, `write-into-code` or `debug-lure`, as `a-judge-requests` defines them,
  and the instruction "This message would put a secret where it shouldn't go. Write the reply you
  would send the agent, then one sentence on why." **Every question names `c-secret-instead`.**
  A full-credit reply says the learner will put (or has put) the secret into the named host's
  settings themselves, under the setting's name, and tells the agent it is there; the sentence
  gives both reasons: the chat is kept and can be shared, and an agent holding the secret can
  write it into a file that gets committed. A scenario has three or four questions.
- **worked example:** write a reply aloud for a `paste-in-chat` message, in the pattern "I've added
  it in Kettle's settings as `DATABASE_URL`; use that, and don't put it in any file", then say
  why.
- **doesn't show:** the question says the message is unsafe, so a pass doesn't show the learner
  would notice; that is `c-judge-secret-request`'s. A reply written on paper doesn't show they
  would send it in the middle of a deploy.
- **offer as:** the one where you write: the actual reply you would send your agent when it asks for
  a secret, about 5 minutes.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
