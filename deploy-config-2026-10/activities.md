# Activities: deploy config

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

Nothing at file level.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `c-place-settings` | follow an agent's explanation of a setting it wants: what it is for and where its value comes from | Given an app whose frontend, backend and database are each on a named vendor, and an exchange in which an agent asks for a setting under a name the learner hasn't met, a student asks what it is for and where its value comes from, and the agent answers. The learner says what the setting is for, whose value it needs (the frontend's address, the backend's address, the database's connection details, or nobody's, because a host sets it automatically, as with `PORT`), and whether it is a secret. It passes when all three are right, including when the setting belongs to one part but holds another part's address, such as the backend's allowed origin holding the frontend's address, and when the agent's answer names only a vendor that hosts two parts. Finding the value on the vendor's site, and what to do with a secret, are not part of it. |
| `c-handle-secret` | keep a secret out of the agent's chat and the app's code | Given a message from an agent deploying an app that asks for a value or proposes a step, says whether they would go along with it, and if not, what they would do instead and why. It passes when they decline to paste a secret into the chat or to let the agent write one into the code or the repository; instead put it straight into the host's settings and tell the agent it is there; give as the reason that the chat is kept and can be shared, and that a secret in a file can be committed; and go along with a request that involves no secret, such as pasting the backend's address. Dealing with a secret that has already leaked is not part of it. |

## Coverage

<!--
  Derivation convention: an activity carrying `checks` sits only in the `checks` cell, never in
  `study`. No orientation row: goals.md has no orientation goal, because cloud-hosting and
  database-hosting come first and lay the area out.
-->

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `c-place-settings` | `a-sort-setting-answers` | `a-read-described-exchange` | The Depth in goals.md includes asking the agent when you don't know what a setting is for. No check tests that: every check supplies the question already asked and a correct answer. A pass shows the learner can follow a good explanation, not that they would ask for one or spot a wrong one. |
| `c-handle-secret` | `a-judge-agent-requests` | `a-handle-described-requests` | Every activity for this goal asks the learner to judge messages on paper, in calm conditions. None shows they would notice a risky request in the middle of a deploy. Treat a pass as "knows what to do", and check during Problem Set 3 whether they did it. |

---

## Activities

### `a-sort-setting-answers`

- **serves:** `c-place-settings`
- **supports:** deepen
- **artifact:** `tasks/sort-setting-answers.md`, written for this topic. It describes Crumbs, a
  React, Express and database app shaped like the learner's Problem Set 2 app, and four made-up
  vendors: three from cloud-hosting's bank (Brightpage, Kettle, Harbor) and Larder, a database
  host. Then six exchanges, each shown as a setting's name and the agent's answer to "What is this
  for, and where does its value come from?". The learner sorts the six by whose value each needs
  and marks the secrets. The key, one row per setting with its near-miss, is in
  `tasks/sort-setting-answers-key.md`, for the tutor only. One sitting does the whole set. 10 to
  15 minutes. Nothing to run.
- **verified:** 2026-10-04
- **learner does:** reads the task file, puts each of the six settings in one of the four groups
  (the frontend's address, the backend's address, the database's connection details, or nobody's
  because a host sets it), says in a few words what each is for, marks each secret, and says in a
  sentence or two the rule they sorted by. Writes all of it before the tutor comments.
- **tutor role:** critic
- **tutor does:** shows the task file, never the key. Takes the whole sort and the rule before
  commenting. For each placement that disagrees with the key, asks one question built from the
  key's _what decides it_ column rather than giving the verdict ("the server reads
  `CLIENT_ORIGIN`; whose pages is it letting in?"). If the placement still differs, gives the
  key's verdict and its reason. If the stated rule sorts by the setting's name or by where it is
  entered, tests it against items 1 and 2. If it looks up which vendor the answer names, tests it
  against item 5, where Harbor hosts two parts and the vendor alone doesn't settle it. If the learner asks how to find a value on a vendor's
  site, says that isn't part of this topic; if they ask what to do with the secret, says that is
  the other capability, `c-handle-secret`.
- **done when:** the sort matches the key, with at most one question per item, and the stated
  rule sorts by what the value is (whose address, or what it unlocks), not by the setting's name
  or where it is entered. A rule that looks up the vendor is enough only if it also says what to
  do when one vendor hosts two parts. No `checks`: the six answers come in one set with the key
  discussed afterwards, so the learner has seen every case with its verdict. The checks use
  settings named differently.
- **offer as:** the quickest way in, 10 to 15 minutes, nothing to run: six short agent answers to
  sort, with the near-misses (a name that says "frontend" holding the backend's address, an
  origin setting on the backend, "your Harbor address" when Harbor hosts two parts, a token that
  is a secret though it isn't an address) all in one set. Made-up vendors, so nothing goes stale.
- **check note:** The six items come with their key discussed in one sitting, so redoing the set
  after a miss shows nothing. If `done when` isn't met, move to the worked example in
  `a-read-described-exchange` and an Easy pairing there, rather than repeating the sort.

### `a-read-described-exchange`

- **serves:** `c-place-settings`
- **supports:** attempt
- **checks:** `c-place-settings`
- **artifact:** no external source. A hosting line and two exchanges, written by the tutor per the
  generator below. 10 minutes.
- **verified:** 2026-10-04
- **learner does:** reads the hosting line and both exchanges, then writes alone, for each, what
  the setting is for, whose value it needs (one of the four), and whether it is a secret. Hands
  it to the tutor.
- **tutor role:** none
- **tutor does:** builds the instance per the generator and writes the key into the record before
  showing anything: for each exchange, what the setting is for in a line, whose value it needs,
  and whether it is a secret. Shows the hosting line and both exchanges. Waits, writing down any
  help word for word. Sends the adjudicator the hosting line, both exchanges, the key, the
  learner's answer verbatim and every piece of help, and tells it the attempt is met only if both
  exchanges are answered right. After the ruling, tells the learner what was missed or named
  wrongly. Labels the attempt `a-read-described-exchange/<first shape>+<second shape>`. A remark
  about finding the value on a vendor's site, or about what to do with a secret, is neither
  credited nor counted against them: the tutor tells the adjudicator to disregard it.
- **done when:** criterion met with no help, on both exchanges of a counting instance.
- **kind:** generator
- **generator:** fixed: the app has a React frontend, an Express backend and a database, shaped
  like Problem Set 2, and a hosting line names the made-up vendor each part is on, with each
  vendor's offer in a line, as `tasks/sort-setting-answers.md` describes them. Brightpage, Kettle,
  Harbor and Larder may be reused, or new vendors invented on the same pattern; the hosting line
  says that the database host's connection details include a password. Each exchange has three
  parts: the agent's request, naming one setting; the student's question, asking what it is for
  and where its value comes from, worded as a student might; and the agent's answer, one to three
  sentences, true to the hosting line. The answer says what the value is used for and where to
  copy it from, naming a vendor or a dashboard, but never in the words "the frontend's address"
  or "the backend's address". Each setting's name is invented each time (for example `SITE_URL`,
  `CORS_WHITELIST`, `REMOTE_DB`, `VITE_SERVER`), and is never `PORT`, `VITE_API_URL`,
  `ALLOWED_ORIGIN`, `DATABASE_URL`, or a name used in `tasks/sort-setting-answers.md` or
  `tasks/judge-agent-requests.md`, all of which the learner may have met. Each exchange takes one
  of these shapes:
  - `plain` (Easy): the name says plainly whose value it holds; not a secret.
  - `host-sets` (Easy): a value the host provides itself, which the agent says not to add.
  - `secret-db` (Medium): the database's connection details, as a connection string or as a
    token or password on its own, under a name that doesn't say "secret", "password" or "key"
    (for example `REMOTE_DB`, `STORE_LINK`); a secret.
  - `shared-cross` (Hard): one vendor (like Harbor) hosts the frontend and the backend, each with
    its own address, and the setting is read by one of them but holds the other's address: a
    backend setting holding the frontend's address (the pages it accepts requests from), or a
    frontend setting holding the backend's address under a name that points the wrong way. The
    agent's answer names only the vendor ("use your Harbor address"), so the vendor alone doesn't
    settle whose address it is.
  **A counting instance is two exchanges: one `shared-cross` and one `secret-db`, in either
  order.** Together they carry both cases the criterion names (a setting holding another part's
  address, and an answer naming only a vendor that hosts two parts) and a secret that has to be
  recognized, and the bar is one unaided pass. Any other pairing is for the worked example and
  for a retry with help after a miss. For review visits, run
  `served.mjs deploy-config-2026-10 c-place-settings` and vary which part's address the
  `shared-cross` setting holds from the last one served.
- **worked example:** work one Easy exchange aloud: say what the agent's answer says the value is
  used for, then ask whose address that is or what it unlocks, then whether someone holding it
  could get into something. At the first level of help on a real attempt, ask only "where does
  the value you would copy actually point?"
- **doesn't show:** the exchange already holds a good question and a clear, correct answer, so a
  pass doesn't show the learner would ask the question themselves, or could make sense of a
  vague or wrong answer. Vendors are made up, so a pass says nothing about real dashboards. The
  learner knows a check is on.
- **offer as:** the check that's available now: two exchanges the tutor writes, 10 minutes, nothing
  to run, built so the hard cases and a secret both come up.
- **check note:** Leave out the sentence saying the database host's connection details include a
  password. With it, the secret question for a connection string is answered by the setup instead
  of by the learner. A counting instance never includes a value the host sets itself. If the
  learner has not shown they know that case (item 4 in `a-sort-setting-answers`), check it
  informally. It is not part of what a pass shows.

### `a-judge-agent-requests`

- **serves:** `c-handle-secret`
- **supports:** deepen
- **artifact:** `tasks/judge-agent-requests.md`, written for this topic: Crumbs, with its frontend
  on Brightpage, its backend on Kettle and its database on Larder, and three pairs of messages
  from the agent deploying it. Each pair has one message to decline and one to go along with. The
  key, one row per message with its near-miss, is in `tasks/judge-agent-requests-key.md`, for the
  tutor only. One pair a sitting, 5 to 10 minutes. Nothing to run.
- **kind:** bank
- **bank:** three pairs, named `A`, `B` and `C`. To pick the next, run
  `served.mjs deploy-config-2026-10 c-handle-secret` and take the first pair not yet served, in
  the order A, B, C that the key gives. Label the attempt `a-judge-agent-requests/<pair>`, for
  example `a-judge-agent-requests/B`. Stop when done when has been met once, and offer
  `a-handle-described-requests`; using up the bank is not the target.
- **verified:** 2026-10-04
- **learner does:** reads the header and the one pair served, then says for each message whether
  they would go along with it, and for one they wouldn't, what they would do instead and why.
  Writes both answers before the tutor comments.
- **tutor role:** critic
- **tutor does:** shows the header and the one pair, never the key file. Takes both answers before
  commenting. Where an answer disagrees with the key, asks one question built from the key's
  _what decides it_ column rather than giving the verdict (for B1, "in this message, where does
  the connection string go on its way from Larder to Kettle?"). If a decline leaves out what to do
  instead, asks "so what would you do with the value?"; if it leaves out the reason, asks "why
  not, if the agent is the one setting it up?". If an answer still differs from the key after
  that, gives the key's verdict and its reason, and moves on. If the learner asks what to do once
  a secret has been pasted, says that belongs to a later topic, in session 13.
- **done when:** both answers match the key, with at most one question each, and the decline says
  what to do instead and gives both reasons: the chat is kept and can be shared, and a secret in a
  file can be committed. No `checks`: the three pairs share one app and one set of vendors, and
  each sitting ends with the key discussed, so by the second pair the learner has been told the
  pattern.
- **offer as:** 5 to 10 minutes, one pair at a time, nothing to run. Each pair puts a request to
  decline beside one that is fine, so declining everything doesn't work, and pair B shows the safe
  pattern to copy: the agent names the setting and you carry the value between dashboards
  yourself.
- **check note:** The `learner does` line says "for one they wouldn't". Read it as "for any they
  wouldn't", and don't tell the learner that each pair has exactly one to decline.

### `a-handle-described-requests`

- **serves:** `c-handle-secret`
- **supports:** attempt
- **checks:** `c-handle-secret`
- **artifact:** no external source. A hosting line and a pair of agent messages, written by the
  tutor per the generator below. 5 to 10 minutes.
- **verified:** 2026-10-04
- **learner does:** reads the hosting line and both messages, then writes alone, for each, whether
  they would go along with it, and if not, what they would do instead and why. Hands it to the
  tutor.
- **tutor role:** none
- **tutor does:** builds the pair per the generator and writes the key into the record before
  showing anything: which message to decline, what to do instead, and the two reasons. Shows the
  hosting line and both messages. Waits, writing down any help word for word. Sends the
  adjudicator the hosting line, both messages, the key, the learner's answer verbatim and every
  piece of help. After the ruling, tells the learner what was missed. Labels the attempt
  `a-handle-described-requests/<secret shape>+<harmless shape>`.
- **done when:** criterion met with no help, on both messages of one counting pair.
- **kind:** generator
- **generator:** fixed: the app has a React frontend, an Express backend and a database, shaped like
  Problem Set 2, each on a made-up vendor named in a hosting line, which says that the database's
  connection string includes its password. Each instance is a pair, because the criterion needs
  both a decline and a go-along: one message involving a secret and one involving none, in either
  order. Never reuse a message from `tasks/judge-agent-requests.md`. Never a message about a
  secret that has already been pasted somewhere, since that case is excluded. Every secret shape
  routes the secret through the agent, so both of the criterion's reasons apply to it: the chat
  is kept, and an agent holding the secret can write it into a file that gets committed. The key
  expects both. The secret message takes one of these shapes:
  - `paste-in-chat` (Easy): asks for the secret to be pasted so the agent can set it up.
  - `write-into-code` (Medium): asks for the secret to be pasted so the agent can put it in a
    source file, with a convenient reason ("so it works the same everywhere").
  - `debug-lure` (Hard): asks for the secret indirectly, as a copy or screenshot of the dashboard
    page that shows it, or the output of a command that prints it, to "check" something.
  The other message takes one of these:
  - `public-address` (Easy): asks for the frontend's or the backend's address to be pasted.
  - `dashboard-instruction` (Hard): tells the learner to add a setting on the host themselves and
    paste the secret there, naming the secret but never asking for it.
  **A pair counts only if at least one of its messages is Medium or Hard.** An Easy pair is for the
  worked example and for a retry with help after a miss. For review visits, run
  `served.mjs deploy-config-2026-10 c-handle-secret` and serve a pair with shapes the learner
  hasn't had.
- **worked example:** work an Easy pair aloud: for each message, say what value would pass through
  the chat or into a file, whether holding that value lets someone into something, and if so
  where it should go instead. At the first level of help on a real attempt, ask only "does any
  value in this message let someone into something?"
- **doesn't show:** the learner is asked to judge, so a pass doesn't show they would notice such a
  request in the middle of a deploy, while trying to get the app working. Vendors are made up.
  The learner knows a check is on.
- **offer as:** the check that's available now: a pair the tutor writes, 5 to 10 minutes, nothing to
  run, with one message to decline and one that is fine, so refusing everything fails.
- **check note:** Do not tell the learner that a pair always has one message to decline and one
  to go along with. After the bank they may expect it anyway. Watch for answers that decide the
  harder message by elimination ("the other one was obviously bad, so this one must be fine").
  When a pair counts only because of its harder message, write that message first and make the
  easier one less obvious, so the harder one is judged on its merits. A `dashboard-instruction`
  message names a secret but routes it from one dashboard to another, never through the chat.
  Going along with it is correct, because it is the criterion's own "instead" step. Tell the
  adjudicator so when you send the key.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
