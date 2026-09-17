# Activities: coding agents

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

## Check notes

2026-09-17. For `c-choose-model` and `c-split-chats`, every check hands the learner a described
situation with the deciding detail on the page, as those criteria ask. A met goal therefore shows
they can judge a described situation, not that they would notice the moment in their own work,
which is the use Depth names; each check says so in `doesn't show`, and it holds whichever check was
passed.

**On `c-choose-model`.** Both checks count "raise the reasoning effort first" on the worth-trying
side, so a met goal does not show the learner would ever choose a stronger model over more effort on
the current one.

**On `c-split-chats`.** Neither check shows the learner can tell when saving tokens is a reason to
split. Independence or a fresh start applies to every split in the generators' lists, and neither
entry says how to rule a split answer naming both reasons where the record lists one; on the
criterion's wording (names a reason that applies) it meets it. A learner who names independence on
every split, or both reasons on every split, each tied to a detail, can pass either check.

**On `c-ask-cost-estimate`.** Both checks rule an accurately reported wrong basis (running totals
added up, reasoning tokens counted twice) as meeting the criterion, so a met goal does not show the
learner would catch an estimate several times too high. Depth asks for an estimate they can trust
and most of the study activities teach exactly that, but no check rules on it. In both checks the
reasons a bill could differ can also come from the agent's replies; see each check's note.

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `c-choose-model` | tell when a better model might be worth trying, and when it is not | given a few short situations from work with an agent, some where a better model is worth trying and some where it is not, says which is which and gives a reason for each that comes from the situation described. A general preference for cheaper, or for better, does not meet it. |
| `c-split-chats` | tell when to split work off into a new chat or a subagent, and when to keep going | given a few short situations partway through work with an agent, some where splitting helps and some where it would lose something the next step needs, says which is which. When arguing for a split, names a reason that applies (independence/fresh start vs. saving tokens) and ties it to something in the situation. Naming a reason without that tie does not meet it. |
| `c-ask-cost-estimate` | ask an agent what a piece of agent work cost | Can ask the agent to estimate what a run that has already happened cost, such as one chat. Can say what the figure it gives back is based on: which model's prices, and which token counts. Can say why that figure may differ from what was actually billed. "It's only an estimate" does not meet it. |

## Coverage

| goal | study | checks | notes |
| ---- | ----- | ------ | ----- |
| `c-choose-model` | `a-read-codex-model-guide`, `a-contrast-model-pairs` | `a-sort-model-situations`, `a-judge-model-switch-log` | see Check notes |
| `c-split-chats` | `a-read-codex-chat-habits`, `a-explain-superpowers-handoffs` | `a-sort-split-situations`, `a-critique-split-narrative` | see Check notes |
| `c-ask-cost-estimate` | `a-watch-estimate-narrated`, `a-critique-flawed-estimates` | `a-estimate-own-chat`, `a-estimate-scratch-log` | see Check notes |

---

## Activities

### `a-read-codex-model-guide`

- **serves:** `c-choose-model`
- **supports:** orient, deepen
- **artifact:** OpenAI's Codex documentation, "Models", the section "Choosing Astra, Sol, Terra, and
  Luna" with its subsections "Where each model shines", "Pick a reasoning effort" and "Know when to
  use Max or Ultra", https://learn.chatgpt.com/docs/models#choosing-astra-sol-terra-and-luna (free, no
  account, about 400 words, 5 minutes to read; 20 to 25 minutes for the activity). It describes
  Sol as for "ambiguous, difficult, or high-value tasks", Terra as "the pragmatic all-rounder" for
  everyday work, and Luna as for "clear, repeatable tasks" where "you know what a good result looks
  like". On reasoning effort it says to use the lowest effort that produces the result you need and
  to raise it for tasks that need more planning, analysis or checking. The page is written for
  people who sign in with ChatGPT: the Power slider, Max and Ultra it mentions may not be offered
  through U-M's gateway, where the models on offer include gpt-5.6-sol, gpt-5.6-terra, gpt-5.6-luna
  and gpt-5-mini. U-M's price list also includes gpt-6-astra, but whether Astra works from Codex
  through the gateway has not been checked. The page gives no prices.
- **verified:** 2026-09-17
- **learner does:** reads the section once. Then, before the tutor says anything, writes three short
  lines, one each for Sol, Terra and Luna: a moment from their own work with Codex so far, or one
  they expect in the session 7 lab, where that model would be the right pick, and the detail of that
  moment that makes it right. Then writes one moment where switching up from the course default
  (gpt-5.6-luna at medium) would not be worth trying, and why. For any line where they have no such
  moment, takes a situation from the tutor instead, makes the call on it (which model, or whether
  switching up is worth trying) and names the detail that decides it. Answers each near-miss the
  tutor sends back. Ends by writing, in their own words, two or three rules of thumb for when a better
  model is worth trying, each naming something you could see in a situation, not "when it matters"
  or "to be safe".
- **tutor role:** socratic questioner
- **tutor does:** waits for the lines. Where the learner has no moment of their own for a line and
  none they expect in the lab, supplies a situation of two or three sentences from work like the
  session 7 app, without saying which model fits or whether switching up is worth trying, and waits
  for the learner's call on it. For each line, replies with one near-miss that changes a single
  detail: "you said Sol for the database design; still Sol if the plan already spells out every
  table?", or "Luna for renaming a component; still Luna if the rename runs through the API route
  and the SQL query too?". Treats "Sol is smarter" or "Luna is cheaper" as a general preference, and
  asks what in the situation makes it matter here. Keeps the two dials apart when the learner blurs
  them: reasoning effort is set beside the model, so "raise the effort first" is a fair answer in a
  situation where something stronger is worth trying, and the checks count it on that side; it is
  not an argument that more capability is not worth trying. Adds the rule the page does not state:
  when the agent is failing because something is missing (the real error message, the right file, a
  server that is not running), a better model does not supply it. Does not quote prices.
- **done when:** the learner has two or three rules of thumb of their own, each tied to something
  visible in a situation, and says they could sort a handful of situations into worth trying and
  not worth trying with their rules and the page beside them.
- **offer as:** the vendor's own words about what each model is for, short, with your own work
  supplying the examples. The quickest way in and the most general: it describes the models, not
  the moments in a working session when you would switch, so the rules have to come from you. Take
  `a-contrast-model-pairs` instead if you would rather be handed situations than think of them.

### `a-contrast-model-pairs`

- **serves:** `c-choose-model`
- **supports:** deepen
- **artifact:** Superpowers, the plugin used in the session 7 lab, skill "subagent-driven-development":
  the section "Model Selection", and under "2. Handle the report" the list for a BLOCKED report,
  https://github.com/obra/superpowers/blob/main/skills/subagent-driven-development/SKILL.md (free,
  no account; the two parts are about 400 words, 5 minutes; 20 to 25 minutes for the activity). The
  file is instructions to an agent choosing models for its subagents, not a tutorial, and the rest
  of it is detail this activity skips. "Model Selection" sorts work by its shape: mechanical tasks
  with a clear spec on a fast, cheap model; multi-file integration and debugging on a standard one;
  architecture and design on the most capable. It adds that the cheapest models "routinely take
  2-3× the turns on multi-step work", costing more overall. The BLOCKED list separates "a context
  problem" (more context, same model) from a task that "requires more reasoning" (a more capable
  model). The file is on the main branch and changes often; the copy installed in Codex may lag it.
- **verified:** 2026-09-17
- **learner does:** reads the two parts once. Then works through three or four pairs of short
  situations the tutor sets. The two situations in a pair are the same except for one detail. For
  each pair, says which one is worth trying a better model for and which is not worth trying, and
  names the detail that flips it, before the tutor answers. After the last pair, says which line of
  the skill each flipping detail came from, or that none did.
- **tutor role:** socratic questioner
- **tutor does:** builds each pair this way. Writes a base situation of two to four sentences from
  work like the session 7 app or PS2 (a React front end with a SQL backend), with the course default
  (gpt-5.6-luna at medium) running. Makes two copies and changes exactly one detail, taking each pair's
  detail from a different line of this list: the plan task includes the complete code, or only a
  prose description of it; the change touches one file, or the front end, the API route and the SQL
  schema together; the agent has failed three times with the error and the relevant files already in
  the chat, or has failed because the error it was given came from a different file; the work is a
  mechanical edit, or a design decision with trade-offs (how to store dates, where state should
  live); the cheap model finished in a few turns, or has taken a dozen turns re-reading the same
  files. Keeps everything else word for word the same and shuffles the order within the pair. When
  the learner names the wrong detail, points at the one that differs and asks what it changes.
  Accepts "raise the reasoning effort first" on the worth-trying side if it is tied to the detail.
  After each pair, asks for the rule it taught in one sentence.
- **done when:** the learner has named the flipping detail correctly in at least three pairs and
  says they could apply the same rules to situations that are not paired, with the skill beside
  them.
- **offer as:** handed situations rather than asked for them, and in pairs, so the one detail that
  matters is the only thing that changes. The rules come from a working tool you will use in session
  7 and at session 8, not from product descriptions, and they include two cases the Codex page leaves
  out: a stuck agent that needs information rather than a better model, and a cheap model that ends
  up costing more because it takes more turns. The pairing makes each call easier than a real one,
  which is why this cannot check anything.

### `a-sort-model-situations`

- **serves:** `c-choose-model`
- **supports:** attempt
- **checks:** `c-choose-model`
- **artifact:** no external source. A set of short situations the tutor writes per the generator
  below. 15 to 20 minutes.
- **learner does:** reads a set of four to six short situations from partway through work with a
  coding agent. For each, writes whether a better model is worth trying or not worth trying, and a
  reason that points at something in that situation. Answers all of them before hearing any
  answer, and is not told how many of each there are.
- **tutor role:** none
- **tutor does:** builds the set before the session and writes down, out of the learner's sight,
  each situation's intended answer and the detail that decides it. The judge rules from that record
  and the learner's answers, so both are kept verbatim. Two kinds of answer that neither label names
  are ruled this way, in both checks for this goal. "Raise the reasoning effort first" counts as worth
  trying, since it says more capability is what the situation lacks: right where the record says
  worth trying and its reason is tied to the deciding detail, wrong where the record says not worth
  trying. "A better model would not help, it is missing information" counts as not worth trying, and
  its reason holds only if what it names is in fact missing from the situation as written. Hands over
  the set and waits. Afterwards goes through any the learner got wrong, asking what in the situation
  they were reacting to.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** write four to six situations of two to four sentences each, set in work like the
  session 7 app or PS2 (a React front end with a SQL backend) in Codex, naming the model and
  reasoning effort in use (usually the course default, gpt-5.6-luna at medium). The two labels are
  worth trying and not worth trying. Include at least two of each, in shuffled order. Build each
  situation around one deciding detail, and use no detail twice in a set. Worth trying: the agent
  has proposed the same fix three times with the error and the relevant files already in the chat;
  an open design decision with real trade-offs (how to split the tables, where state should live);
  one change that has to agree across the front end, the API route and the SQL schema; a mistake
  would be costly (a change to a table holding data the learner cares about, a last review before
  submitting); the cheap model has taken many turns going round the same files on a multi-step task.
  Not worth trying: a mechanical edit with a clear spec (rename a prop in two files, change a
  button's text); a plan task that already contains the complete code; summarizing or reformatting
  (a commit message, turning test output into a checklist); the current model already produced
  something that works and the learner wants it "better" with no defect named. Hold fixed: every
  situation has one defensible answer under the two labels; none turns on prices or on a model the
  learner has not met; the wording does not hint ("tricky", "simple", "important"). Easy: four
  situations with unmistakable cues. Medium: five or six, one of which carries a surface cue
  pointing the wrong way (a long, alarming error message that turns out to be a one-line typo fix).
  Hard: add a situation where the agent keeps failing because information is missing (the pasted
  error came from a different file, the server is not running), whose answer is not worth trying
  because no model supplies what is missing, alongside a repeated failure where the information is
  all there. Only a set at Medium or Hard can finish the goal; Easy is for practice and for the
  worked example's situations. Never reuse a situation across sets.
- **worked example:** work two situations aloud that are not in the set, one each way, saying the
  deciding detail and why it decides. At the first level of help, give only the question to ask of
  each situation: is what's missing more capability, some information, or nothing at all?
- **doesn't show:** the situations are written for the learner with the deciding detail already on
  the page, so a pass does not show they would notice a decision point in the middle of their own
  work or pick the detail out of a long chat. Nothing is run, so it shows nothing about whether the
  better model would in fact have helped. It does not separate a better model from higher reasoning
  effort, the other dial beside the message box.
- **offer as:** the plain version of the real thing: a handful of situations, your call on each,
  nothing paired to lean on. Quick, and fresh situations every time this comes back in review.

### `a-judge-model-switch-log`

- **serves:** `c-choose-model`
- **supports:** attempt
- **checks:** `c-choose-model`
- **artifact:** no external source. A short invented log of one classmate's working session, written
  by the tutor per the generator below. 15 to 20 minutes.
- **learner does:** reads a classmate's log of an evening's work with Codex. Each entry says what was
  happening, which model was running, which model they switched to or stayed on, and the reason they
  give. For every entry, sets the classmate's choice aside and writes whether, at that moment, a
  better model was worth trying or not worth trying, with a reason taken from what the log describes.
  Judges each entry from where the classmate actually was after their earlier choices, right or
  wrong: where they were already on a stronger model, the question is whether staying on it was worth
  it. Then says, for each entry, whether the classmate's own reason would have held up.
- **tutor role:** none
- **tutor does:** builds the log before the session and records, out of the learner's sight, the
  intended answer and the deciding detail for each entry, each from the state the classmate's
  earlier choices actually left; keeps those and the learner's answers verbatim for the judge. Rules
  effort-first and missing-information answers as `a-sort-model-situations` says. On an entry where
  the classmate was already on a stronger model, worth trying means worth staying on it, so an
  answer to drop back to Luna at a higher effort still counts on that side. Waits during the
  attempt. Afterwards asks, of any entry the learner got wrong, whether they were reacting to the
  situation or to the classmate's decision.
- **done when:** criterion met with no help. The ruling is on the learner's own call and reason for
  each entry. Whether they said the classmate's reason held up is practice and not part of the
  criterion.
- **kind:** generator
- **generator:** write a log of four to six entries from one working session on a project like PS2
  (a React front end with a SQL backend) in Codex, starting on the course default (gpt-5.6-luna at
  medium). Each entry is two or three sentences of situation naming the model then running, then the
  classmate's choice (switched up, switched back down, or stayed), then their reason in one line.
  Take situations from the two lists in `a-sort-model-situations`, at least two worth trying and at
  least two not worth trying, one deciding detail each. Each entry starts from whatever the
  classmate's earlier choices left, and its intended answer is recorded from there: after a switch
  up, an entry of routine work on Sol asks whether staying on Sol is worth it, and its answer is not
  worth trying (drop back down). Give the classmate generic or misdirected reasons ("Sol is the
  smartest", "gotta save my $50", "just in case", or a reason naming some detail other than the
  deciding one), on right decisions as well as wrong ones, so that no reason can be copied. Hold
  fixed: at least one decision is right; the log reads as one plausible evening, in order; nothing hints which entries
  are wrong; the number of wrong decisions is not announced. Easy: four entries with unmistakable
  cues and one wrong decision. Medium: five entries, two wrong decisions (one switch up that was
  not worth trying, one stay on Luna when a better model was worth trying), one right decision
  given a wrong reason, and one entry whose deciding detail is not restated in it but was set in an
  earlier entry (the error and the relevant files were pasted into the chat two entries back), so
  it has to be carried forward. Hard: six entries, two or three wrong decisions, a stay on Luna that
  was right for the wrong reason, an entry whose deciding detail was set earlier, and an entry where
  the agent keeps failing for want of information the classmate never gave it (not worth trying,
  since no model supplies it). Only a log at Medium or Hard can finish the goal; Easy is for practice
  and for the worked example's entry.
- **worked example:** work one entry that is not in the log aloud: read the situation with the
  choice covered, say worth trying or not worth trying and the deciding detail, then uncover the
  choice and the classmate's reason and say whether that reason would have held up. At the first
  level of help, say only: cover the classmate's choice before you judge.
- **doesn't show:** the classmate's choice is on the page, so a learner can lean on second-guessing
  it instead of reading the situation, and the tutor's question afterwards is the only guard. As
  with `a-sort-model-situations`, the deciding details are on the page rather than found in a live
  chat (from Medium up one has to be carried from an earlier entry, which is as close as this gets),
  nothing is run, and a better model is not separated from higher reasoning effort.
- **offer as:** someone else's decisions to pick apart instead of a blank set to sort, which is
  closer to what you will do after an evening of PS2: look back and ask whether a switch was worth
  it. Harder than it looks, because some right decisions come with bad reasons and you have to
  supply the real one.

### `a-read-codex-chat-habits`

- **serves:** `c-split-chats`
- **supports:** orient, deepen
- **artifact:** two short sections of OpenAI's Codex documentation, read together (free, no account,
  about 450 words between them, 5 minutes; 20 to 25 minutes for the activity). First, "Best
  practices", the section "Organize long-running chats" and the last bullet under "Common mistakes",
  https://learn.chatgpt.com/guides/best-practices. It says to "keep one chat per coherent unit of
  work", that staying in the same chat "preserves the reasoning trail", and that one chat for an
  entire project "leads to bloated context and worse results over time". Its list of slash commands
  is for the command-line version and can be skipped. Second, "Subagents", the section "Why subagent
  workflows help", https://learn.chatgpt.com/docs/agent-configuration/subagents. It names context
  pollution and context rot, says to move noisy work (exploration, test logs, stack traces) off the
  main chat and have subagents return summaries, and the same page says earlier that subagent
  workflows "consume more tokens than comparable single-agent runs". Neither section explains why a
  long chat costs more per message; the tutor supplies that.
- **verified:** 2026-09-17
- **learner does:** reads both sections. Then, for each piece of advice (one chat per unit of work;
  stay in the chat when that preserves the reasoning trail; do not run a whole project in one chat;
  move noisy work to a subagent), writes a moment from their own work with Codex so far where it
  applied or would have (or, where they have none yet, one they expect in the session 7 lab, or one
  the tutor supplies), and says whether they split or kept going. For the three pieces about
  splitting, names a reason that applies to a split there (a fresh start or independence, or saving
  tokens); for staying in the chat to preserve the reasoning trail, says instead what splitting would
  have lost there. Writes first, then answers the tutor's near-miss on each. Ends by writing one
  situation where splitting would lose something the next step needs, and what that something is.
- **tutor role:** socratic questioner
- **tutor does:** before the learner starts, supplies what neither section says, in two or three
  sentences: every message in a chat sends the whole conversation so far to the model again, as
  input tokens, so a long chat makes every later message cost more; prompt caching can make that
  repeated input cheaper, but only while the cache lasts, and on U-M's gateway cached input has shown
  up on some turns and not others. Where the learner has no moment of their own for a piece of
  advice and none they expect in the lab, supplies one in two or three sentences from work like the
  session 7 app, without saying whether to split. Then waits for the lines. For each, replies with a
  near-miss that changes one detail: "you split after brainstorming; still a good split if the design decision you
  reached never made it into the spec?", or "you called that subagent a token saving; the page says
  subagent workflows use more tokens overall, so what is the subagent buying you?". Treats a reason
  with no tie to the moment ("new chats are cleaner") as not yet a reason and asks what in the
  moment makes it apply.
- **done when:** each piece of advice has a moment attached, from the learner's own work where they
  have one, with a reason tied to that moment (for the reasoning trail, what splitting would have
  lost), and the learner says they could sort new situations
  into split and keep going with the two sections beside them.
- **offer as:** the vendor's own advice about chats and subagents, short, applied to chats you have
  already had. The quickest way in, and it covers new chats and subagents both, but it says almost
  nothing about the token side, which the tutor fills in. Take `a-explain-superpowers-handoffs`
  instead if you would rather see a whole workflow built around splitting before judging splits
  yourself.

### `a-explain-superpowers-handoffs`

- **serves:** `c-split-chats`
- **supports:** deepen
- **artifact:** Superpowers, the plugin used in the session 7 lab and in its execution half at session
  8. Passages from two of its skill files, used as a worked example of a way of working built around
  splitting (free, no account; the passages are about 400 words, 10 minutes; 25 to 30 minutes for
  the activity). From "writing-plans",
  https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md: the opening paragraph
  (plans are written "assuming the engineer has zero context for our codebase") and the section
  "Execution Handoff". From "subagent-driven-development",
  https://github.com/obra/superpowers/blob/main/skills/subagent-driven-development/SKILL.md: the
  "Why subagents" paragraph at the top ("They should never inherit your session's context or
  history"); the decision diagram under "When to Use", read as its questions (is there a plan, are
  the tasks mostly independent, and the branch for tightly coupled tasks); the paragraph under
  "Setup" beginning "Conversation memory does not survive compaction"; the paragraph under "The Task
  Loop" beginning "Everything you paste into a dispatch prompt"; and, under "1. Dispatch the
  implementer", the bullet beginning "A dispatch prompt describes one task". These are instructions
  written for an agent, not a tutorial, and they are dense; the rest of both files is detail this
  activity skips. Both files are on the main branch, and subagent-driven-development changes often
  (writing-plans much less); the copy installed in Codex may lag them.
- **verified:** 2026-09-17
- **learner does:** reads the passages with the tutor. Then takes the handoffs in the Superpowers
  flow in two groups, one at a time. First the splits, where work actually leaves the chat running
  the plan: each task goes to a fresh implementer subagent; a separate reviewer subagent checks each
  task. For each split, says what the subagent needs, where that travels (the prompt handed to it,
  or a file it is pointed at), a reason the split serves (a fresh start or independence, or keeping
  tokens down in the chat running the plan) tied to something in the passages, and what would go
  wrong if what travels were missing or thin. Then the write-downs, which are not splits themselves:
  brainstorming ends in a written spec; the spec becomes a written plan, written for an engineer
  with zero context; the chat running the plan keeps a progress file. For each write-down, says what
  it records, what later event it lets the work survive (a split to a fresh subagent or a new chat,
  or a compaction of the same chat), and what would be lost without it. Then finds the place in the
  flow where the skill itself says not to split, and says what splitting there would lose.
- **tutor role:** socratic questioner
- **tutor does:** reads alongside and explains any term on request. Lets the learner go first on
  each handoff. Presses on where it travels, the part learners skip: a split only works if what the
  next step needs is written down somewhere it can read. Asks the counterfactual each time ("the
  brainstorm settled that dates are stored as text, but the spec never says so; what does the
  implementer do?"). Points out, if the learner does not, that the reviewer is kept separate for
  independence (it should not share the implementer's assumptions), not to save tokens; that both
  reasons apply to the implementer split, as "Why subagents" says; and that the "Everything you
  paste" paragraph is the token argument: whatever goes into the chat running the plan is re-read on
  every later turn. Does not ask which reason a write-down serves; if the learner offers one, asks
  which later split or compaction it prepares for. Does not go into ledgers, fix rounds or worktrees
  beyond what a handoff needs.
- **done when:** the learner has said, for each split, what travels and a reason it serves, and for
  each write-down, what it records and which split or compaction it lets the work survive; has named
  the tightly coupled case where the skill does not split, and says they could judge new situations
  the same way with the passages beside them.
- **offer as:** a whole way of working built around splitting, taken apart handoff by handoff, and
  a preview of what Superpowers will do in your session 7 lab and at session 8. Slower and denser
  than `a-read-codex-chat-habits`, since these are instructions written for an agent, but it shows
  what makes a split safe (what the next step needs, written into a file), which the Codex pages only
  imply.

### `a-sort-split-situations`

- **serves:** `c-split-chats`
- **supports:** attempt
- **checks:** `c-split-chats`
- **artifact:** no external source. A set of short situations the tutor writes per the generator
  below. 15 to 20 minutes.
- **learner does:** reads four to six short situations, each partway through work with a coding agent
  and each stopping at a point where the work could be split off (into a new chat or a subagent) or
  kept going. For each, writes split or keep going. For every split, names a reason that applies (a
  fresh start or independence, or saving tokens) and points at the thing in the situation that makes
  it apply. Answers all of them before hearing any answer, and is not told how many of each there are.
- **tutor role:** none
- **tutor does:** builds the set before the session and records, out of the learner's sight, each
  situation's intended answer and the detail that decides it, and for each split which of the
  criterion's two reasons apply (one or both), each with the detail it is tied to. The record uses
  those two categories and no others: independence or a fresh start, which is one reason however it
  is worded, and saving tokens. Keeps the record and the learner's answers verbatim for the judge,
  and tells the judge the record is written in the criterion's two categories. The judge rules this
  way, in both checks for this goal. A split reason meets the criterion when the record lists it and
  the learner ties it to its detail; independence and a fresh start are the same reason, whichever
  word the learner uses; a reason the record does not list does not meet it, however well argued. An
  answer that says to write something down first and then split is ruled on splitting as things
  stand: on a keep-going situation it counts as keep going if it names what the next step would
  lose, and as a split if it does not; on a split situation it counts as a split and still needs its
  reason. Waits during the attempt. Afterwards,
  for each keep-going situation, asks what the next step would have lost; that answer is not part of
  the ruling.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** write four to six situations of three to five sentences each, set in work like the
  session 7 app (built with Superpowers: brainstorm, spec, plan, then execution) or PS2 (a React
  front end with a SQL backend) in Codex. Include at least two where splitting helps and at least
  two where it would lose something the next step needs, shuffled. Use no deciding detail twice in a
  set. For each split situation, record which of the criterion's two reasons apply to it as written,
  independence or a fresh start (one reason, however worded) and saving tokens: both, whenever each
  can be tied to a detail on the page, and one only where the other plainly does not apply. Split,
  with the reasons that apply as described here (change the record if the wording changes what a
  reader could tie a reason to): the spec and plan are saved as files, the chat that produced them
  is full of abandoned ideas, and execution is next (independence or a fresh start; saving tokens
  too if the chat is described as long); the learner wants the code the agent just wrote reviewed by
  something that does not share its assumptions (independence or a fresh start only, since a
  reviewer adds tokens rather than saving them); a question unrelated to the current feature comes
  up mid-task, such as how to install the database on their laptop (independence or a fresh start;
  saving tokens too, since the answer would otherwise be sent again with every later message in the
  feature chat); since the chat was compacted, the agent has started contradicting constraints that
  are written in the spec (independence or a fresh start only); a chat that has run for hours
  through many file reads, where the next several requests are small independent edits that need
  none of it (both reasons); coming back the next morning to a very long chat for a one-line fix
  unrelated to anything in it (both reasons).
  Keep going: mid-debugging, several causes have been ruled out in the chat, nothing is written
  down, and the next step builds on what was ruled out; a design change was just agreed in the chat,
  is not in the spec yet, and the next step implements it; two pieces being designed together (a
  form and the API route it calls) where each depends on choices in the other; the learner is about
  to open a new chat and ask it to "fix the bug we were talking about". Hold fixed: every situation
  has one defensible call, split or keep going; a split situation never asks the learner to choose
  between a new chat and a subagent, and either counts; nothing turns on numbers; at every level, at
  least one split situation is one where only one reason applies (the reviewer, the agent
  contradicting the spec since compaction, or the saved spec and plan in a chat not described as
  long), so that saving tokens given on every split does not pass. Easy: four situations with
  unmistakable cues. Medium: five or six, including a long chat that still holds something the next
  step needs, so the answer is keep going despite the length. Hard: add a split where the tempting
  reason is the wrong one (a reviewer subagent a learner may justify as saving tokens, when subagent
  workflows use more tokens overall and the reason that applies is independence or a fresh start),
  and a keep-going situation whose surface cue points toward splitting: the chat has run for hours
  and was compacted once, but what the next step needs was settled after that compaction and is not
  written down anywhere. Only a set at Medium or Hard can finish the goal; Easy is for practice and
  for the worked example's situations.
- **worked example:** work two situations aloud that are not in the set: one split, naming a reason
  that applies and the detail it is tied to; one keep going, naming what would be lost. At the first
  level of help, give only the question to ask of each situation: does the next step need anything
  that exists only in this chat?
- **doesn't show:** the situations are described for the learner, so a pass does not show they would
  stop at the right moment in their own work, or that they would write down what the next step needs
  before splitting, which is what makes a split safe. The criterion asks for no reason on a
  keep-going call, so those answers are only right or wrong. Where the record lists both reasons for
  a split, either passes, so a pass does not show the learner can tell which one matters more there.
  Every split in these lists where only one reason applies is one for independence or a fresh start,
  so a learner who gives that reason on every split is not caught the way one who gives saving tokens
  on every split is. Nothing is run, so it shows nothing about how many tokens a split actually
  saves. It never asks them to choose between a new chat and a subagent.
- **offer as:** the plain version of the real thing: a handful of moments, your call on each, with
  the reason for every split tied down. Quick, and fresh situations every time this comes back in
  review.
- **check note:** This file uses "saving tokens" in two senses: fewer tokens sent again in the chat
  that carries on (the unrelated question, the long chat, the "Everything you paste" paragraph in
  `a-explain-superpowers-handoffs`), and fewer tokens overall (the reviewer, and the Codex page's
  point that subagent workflows use more). The reviewer's record uses the second. A learner whose
  only reason for the reviewer is that it keeps the review out of the chat that carries on is
  reasoning as the rest of the file does, and still fails that situation under "however well
  argued". If that is the only miss in a set, say so when going through the answers.

### `a-critique-split-narrative`

- **serves:** `c-split-chats`
- **supports:** attempt
- **checks:** `c-split-chats`
- **artifact:** no external source. A short invented account of a classmate's working session,
  written by the tutor per the generator below. 20 minutes.
- **learner does:** reads a classmate's account of one working session with Codex, in which they
  split work off or kept going at five or six points, each time giving a reason. For each point, sets
  the classmate's choice aside and writes whether splitting there helps or would lose something the
  next step needs, judging from where the classmate actually was after their earlier choices (after a
  split that lost something, the next point starts without it). For every point where splitting
  helps, names a reason that applies (a fresh start or independence, or saving tokens) and ties it to
  something in the account, in their own words rather than the classmate's.
- **tutor role:** none
- **tutor does:** builds the account before the session and records, out of the learner's sight,
  each point's intended answer and deciding detail, taken from the state the classmate's earlier
  choices actually left, and for each split which of the criterion's two reasons apply (independence
  or a fresh start, counted as one reason; saving tokens), one or both, with the detail each is tied
  to, as in `a-sort-split-situations`; also records which point shows an outcome, if any. Keeps
  those and the learner's answers verbatim for the judge. The judge rules only the points with no
  outcome shown, and rules split reasons (independence and a fresh start being the same reason), and
  answers that say to write something down and then split, exactly as `a-sort-split-situations`
  says. Waits during the attempt. Afterwards asks, of any point the learner got wrong (outcome points
  included), whether they were reacting to what happened or to the classmate's choice.
- **done when:** criterion met with no help. The ruling is on the learner's own call and reason at
  each point with no outcome shown, not on whether they caught the classmate out.
- **kind:** generator
- **generator:** write one continuous first-person account, 250 to 400 words, of a classmate's
  session on the session 7 app or on PS2, with five or six decision points taken from the lists in
  `a-sort-split-situations`. At each point the classmate splits or keeps going and says why in a
  sentence. Give them reasons that are generic ("fresh chats are just better", "subagents are
  faster") or that name a reason that does not apply (a token saving claimed for a reviewer
  subagent), on right decisions as well as wrong ones, so no reason can be copied. Each point starts
  from what the classmate's earlier choices actually left: after a split that lost something, the
  next point is in the new chat or subagent without it, and its intended answer is recorded from
  there. What happened after a decision is shown at no more than one point, and that point is
  practice, left out of the ruling. Hold fixed, at every level: the points with no outcome shown
  include at least two where splitting helps, at least one of them a split where only one reason
  applies (as listed in `a-sort-split-situations`), at least two where splitting would lose
  something, and at least one wrong decision; at least one decision is right; the account reads as
  one plausible session, in order; the number of wrong decisions is not announced. Easy: five
  points, one wrong decision, an outcome shown at one other point. Medium: five points, two wrong
  decisions with no outcome shown (one split that lost something the next step needed, such as a
  new chat opened before an agreed change was written down; and one keep-going that should have been
  a split), an outcome shown at one other point, and one ruled point whose deciding detail is not
  restated there but was set earlier in the account (a constraint agreed two paragraphs before and
  never written into the spec), so it has to be carried forward. Hard: six points, two or three
  wrong decisions, no outcomes shown, a deciding detail set earlier as at Medium, and one right split
  given a reason that does not apply. Only an account at Medium or Hard can finish the goal; Easy is
  for practice and for the worked example's decision point.
- **worked example:** work one decision point that is not in the account aloud: with the classmate's
  choice covered, say split or keep going and why, then uncover their choice and reason and say
  whether that reason would have held up. At the first level of help, say only: at each point, find
  what the next step needs and ask where it is written down.
- **doesn't show:** the classmate's choice is on the page, which gives the learner something to react
  against that a real session does not; points with an outcome shown would give their answer away,
  which is why they are not ruled. The deciding details are still on the page, and carrying one
  forward from earlier in the account is the nearest this comes to finding one in a live chat. As
  with `a-sort-split-situations`, it does not show they would stop at the right moment in their own
  work, examines no reason on a keep-going call, does not catch a learner who gives independence or
  a fresh start on every split, and runs nothing.
- **offer as:** a whole session to pick apart instead of separate moments to sort, which is closer to
  looking back over your own evening of PS2. Harder than the plain set, since the decisions run into
  each other, a deciding detail may have been set paragraphs earlier, and some right choices come
  with wrong reasons.
- **check note:** After a wrong split, the easiest way to write the next point shows what was lost:
  the new chat asks what was decided, or gets it wrong. That is an outcome shown for the earlier
  point. It uses up the one outcome the account may show and takes that point out of the ruling,
  which can leave fewer ruled points than Hold fixed requires, and at Hard no outcome may be shown
  at all. Describe where the classmate is at the next point, not how the split turned out, and
  recount the ruled points once the account is written.

### `a-watch-estimate-narrated`

- **serves:** `c-ask-cost-estimate`
- **supports:** orient, deepen
- **artifact:** no external source for the demonstration: one of the learner's own finished Codex
  chats, or, if the tutor cannot read the learner's session logs, an Easy scratch log built as in
  `a-estimate-scratch-log`. 20 to 25 minutes. Two references the tutor draws on. U-M's per-token
  prices, "ITS AI Services Pricing", https://its.umich.edu/computing/ai/pricing: under "U-M GPT
  Toolkit", one table giving each model's prompt and completion rates per 1M tokens, billed monthly
  and "subject to change". An agent asked to read it is refused, so the learner opens it in a browser
  and pastes the rows. And OpenAI's "Prompt caching" guide,
  https://developers.openai.com/api/docs/guides/prompt-caching, the subsection "GPT-5.6 and later"
  under "How caching works" and the bullets under "Monitor cache performance". Those say that cached
  input and cache writes are counted inside input tokens and, at OpenAI's own prices, charged at 0.1
  and 1.25 times the ordinary input rate. U-M's page gives no cached-input or cache-write rate, so
  how the gateway bills them is not known.
- **verified:** 2026-09-17 for OpenAI's "Prompt caching" guide, and for the Codex session log format
  against the openai/codex source. U-M's pricing page 2026-09-17, read in a browser by the
  instructor: it lists gpt-5.6-sol, gpt-5.6-terra, gpt-5.6-luna and gpt-5-mini, with prompt and
  completion rates per 1M tokens only and no cached-input or cache-write rate.
- **learner does:** first, before seeing anything, writes the request they would send their own
  agent to find out what that chat cost. Then watches the tutor carry out the request as an agent
  would, saying before each step what they expect the agent to need next (where the record of the
  chat is, which model it used, which counts, whose prices), and writing down each place the
  demonstration went differently from what they expected. At the end, rewrites their request in the
  light of what they saw, and says in their own words what the figure was based on and two reasons
  the bill could come out different.
- **tutor role:** explainer
- **tutor does:** performs the estimate, narrating what it is weighing and pausing for the learner's
  prediction before each step. Finds the chat's log: on macOS, one file per chat under
  ~/.codex/sessions/YYYY/MM/DD/, or ~/.codex/archived_sessions/ (no dated folders) if the chat was
  archived, named rollout-*.jsonl (the location on Windows has not been checked). Reads the model
  and reasoning effort the log records, and notes whether they changed partway. Makes one false
  start on purpose: adds up the counts from every token_count event, then shows that each event
  carries a running total for the chat so far beside the counts for that one call, so adding the
  running totals counts the early calls over and over, and the last event's running total is the
  chat's total, except in a chat that overran its context window, where Codex resets the running
  total (the total set to the window size, the other counts zeroed) so later totals undercount what
  came before, and in a forked chat, whose running total starts from its parent's and so includes
  the parent's usage. Says in a sentence each that one message from the learner can
  produce several of these events, one per call to the model; that cached input and cache writes are
  parts of the input count, not additions to it; and that reasoning tokens are already inside the
  output count. Looks in the same day's folder for other log files carrying the same session id,
  which is where subagent work turned up on one Mac in September 2026: a reviewer subagent Codex
  started on its own, running a different model, with its own file and its own counts. Has the
  learner open U-M's pricing page in a browser and paste the rows for the models found. Gives the
  estimate with its basis stated, then says why the bill could differ: the prices that apply are
  U-M's, which need not match a vendor's own list and which the page says are subject to change, so
  a figure priced from anywhere else, or from rows that have since changed, can be off; how the
  gateway bills cached input and cache writes, which U-M's page gives no rate for, when cached input
  has shown up on some turns and not others; subagent work in other files; the Toolkit page shows
  spend per key, covering every chat and anything else on that key, never one chat; the estimating
  itself costs tokens. Mentions the practical point that a log can be large, so a good request has
  the agent pull out the counts rather than read the whole file into the chat. Afterwards reads the
  learner's rewritten request and says what a literal-minded agent would do with it. For a learner
  on their own ChatGPT subscription, says that nothing is billed per token, so the figure is what the
  chat would have cost on a Toolkit key.
- **done when:** the learner has a rewritten request of their own and can say, with the demonstration
  still on screen, which model's prices and which counts the figure used and why the bill could
  differ. This activity cannot meet `c-ask-cost-estimate` and carries no `checks`: the tutor did the
  work the agent would do, and the predictions were prompted step by step.
- **offer as:** the one to take before you have asked an agent for a cost yourself. You see what the
  agent has to find and the mistake that makes an estimate several times too high, which a finished
  figure never shows. It needs a live session, and one of your own chats if the tutor can reach your
  logs.

### `a-critique-flawed-estimates`

- **serves:** `c-ask-cost-estimate`
- **supports:** deepen
- **artifact:** no external source for the replies, which the tutor writes as described under
  `tutor does`. 20 minutes. The planted flaws rest on the two references named in
  `a-watch-estimate-narrated` and on a third. U-M's pricing page,
  https://its.umich.edu/computing/ai/pricing, one table of each model's prompt and completion rates
  per 1M tokens, with no cached-input rate, read through the rows the learner pastes from it at the
  start, since an agent asked to read it is refused (see `tutor does`). OpenAI's "Prompt caching"
  guide, https://developers.openai.com/api/docs/guides/prompt-caching. And OpenAI's API pricing page,
  https://developers.openai.com/api/docs/pricing, used only for the flaw that sets OpenAI's list
  against U-M's page.
- **verified:** 2026-09-17 for OpenAI's "Prompt caching" guide, OpenAI's API pricing rows for the four
  models, and the Codex log facts behind the flaw list, against the openai/codex source. U-M's pricing
  page 2026-09-17, read in a browser by the instructor: one table of prompt and completion rates per
  1M tokens, no cached-input rate, gpt-5.6-sol at $5.00 / $30.00, and gpt-5.6-terra, gpt-5.6-luna and
  gpt-5-mini at the same rates as OpenAI's list.
- **learner does:** reads three replies an agent might give when asked what a finished chat cost,
  each with a short description of the chat beside it. For each reply, writes: what the figure is
  based on, as far as the reply says (which model's prices, which counts); anything wrong with that
  basis or missing from it; and one reason the real bill could still differ even if the reply had no
  mistakes. Does all three before hearing any answer, without knowing how many flaws there are or
  whether a given reply has any.
- **tutor role:** critique target
- **tutor does:** opens by having the learner open U-M's pricing page in a browser and paste the
  rows for gpt-5.6-sol, gpt-5.6-terra, gpt-5.6-luna and gpt-5-mini, unless they already pasted them
  earlier in this sitting; the replies are written from those rows, in the session, before the
  learner sees any of them. Writes three replies in the voice of a coding agent, 60 to 120 words
  each, each giving a dollar figure for one finished chat, with a two-line description of that chat
  beside it (for example: two hours on the session 7 app, switched from gpt-5.6-luna to gpt-5.6-sol
  partway; or a PS2 session that sent work to two reviewer subagents). Plants zero, one or two flaws
  in each reply, at least three across the set, with at least one reply that has none, taken from
  this list: every call priced at the course default model although the chat switched; the running
  totals from every token_count event added together; cached input added on top of the input count,
  though it is already inside it; reasoning tokens added on top of output tokens; subagent work in
  separate log files left out; no basis given at all, only a figure; and prices from OpenAI's list
  rather than U-M's page. Plants that last one only in a reply about a chat whose model the tutor
  has just found at a different rate on OpenAI's pricing page than in the pasted rows, and leaves it
  out if it cannot check. On 2026-09-17 that held for gpt-5.6-sol alone of the four (OpenAI's
  standard short-context rates, $4.00 input and $20.00 output per 1M tokens, against U-M's $5.00 and
  $30.00); gpt-5.6-terra, gpt-5.6-luna and gpt-5-mini were the same on both. Keeps each flawed reply
  confident and plausible, with no hedge that points at the flaw, and writes down beforehand which
  flaws are where. Afterwards goes through each reply, confirming or correcting what the learner
  found, and pushes on the "could still differ" answers until each names something specific to this
  chat or this key (how the gateway bills cached input, which U-M's page gives no rate for, is one
  such reason for a chat that shows cached input); "it's only an estimate" gets the question
  "different how, and why?". Has the learner compute nothing.
- **done when:** the learner has found most of the planted flaws, has said the basis of each reply in
  words, and can name at least two specific reasons a figure with no mistakes could still differ from
  the bill, with the replies still in front of them. This activity carries no `checks`: nobody asks
  an agent for anything, so the first part of the criterion is untouched.
- **offer as:** the mistakes without the mechanics: three plausible answers from an agent, and your
  job is to say what each rests on and where it goes wrong. Faster than the narrated demonstration
  and needs no log files, but you never watch a figure being produced, so take
  `a-watch-estimate-narrated` first if you have not seen one.

### `a-estimate-own-chat`

- **serves:** `c-ask-cost-estimate`
- **supports:** attempt
- **checks:** `c-ask-cost-estimate`
- **artifact:** no external source. One of the learner's own finished Codex chats, chosen per the
  bank below; the learner's own Codex agent; and U-M's pricing page,
  https://its.umich.edu/computing/ai/pricing, one table of each model's prompt and completion rates
  per 1M tokens (an agent asked to read it is refused, so the learner opens it in a browser and
  pastes the rows). 15 to 20 minutes.
- **verified:** 2026-09-17 for the Codex session log format, against the openai/codex source. U-M's
  pricing page 2026-09-17, read in a browser by the instructor: it lists gpt-5.6-sol, gpt-5.6-terra,
  gpt-5.6-luna and gpt-5-mini, with prompt and completion rates per 1M tokens only and no
  cached-input or cache-write rate.
- **learner does:** opens a new chat in Codex, not the chat being estimated, and asks the agent in
  their own words to estimate what the chosen chat cost. Reads the reply, and if it does not say
  what the figure rests on, asks until it does. Then, without help, tells the tutor what the figure is
  based on (which model's prices, and which token counts) and why it may differ from what was
  actually billed. Keeps the transcript of the estimating chat, their own requests and the agent's
  replies both.
- **tutor role:** none
- **tutor does:** settles the chat to be estimated with the learner before they start, as the bank
  says, and names it back to the learner by when it happened and what it was about. Waits while the
  learner works with their own agent. Afterwards reads the transcript, checks that the basis the
  learner described is the one the agent actually used, and keeps the transcript and the learner's
  explanation verbatim for the judge. If that basis was itself wrong (the agent added up the running
  totals, or added reasoning tokens on top of output), a learner who reports it accurately still
  meets that part of the criterion, since catching a wrong basis is not part of it; the tutor tells
  the judge so, and points out the error to the learner after the ruling. If the agent could not get
  at the log, the attempt stops there and is not counted as a miss: the location on Windows has not
  been checked, nor whether Codex lets a chat opened in a project read ~/.codex. The learner
  approves the access if Codex asks for it; otherwise the tutor moves to `a-estimate-scratch-log`.
- **done when:** criterion met with no help.
- **kind:** bank
- **bank:** the learner's own finished Codex chats, as many as they have. Each item is one chat,
  named by the filename of its main session log (rollout-<date>T<time>-<id>.jsonl, under
  ~/.codex/sessions/YYYY/MM/DD/, or ~/.codex/archived_sessions/ if the chat was archived); where the
  tutor cannot see the learner's session folder, the learner asks their agent for the filename after
  the attempt. Never serve a chat already used. Pick one new feature at a time. First run: a chat
  from an earlier session that stayed on one model. Later runs, any unused chat of a kind not yet
  used: a chat where the model or reasoning effort was changed partway; a chat long enough to have
  been compacted; a chat that used subagents (from session 8 on); the session 7 lab chat (if the lab
  ran across several chats, they are estimated together as one item, named by the earliest). Once
  every kind has been used, any unused chat. The tutor usually cannot see the learner's session folder, so
  it picks by asking: the learner names a finished chat by its day and topic and says what they
  remember changing in it (the model or reasoning effort partway, subagents they asked for). A
  remembered change of model or effort is enough to aim at that kind. Compaction, and subagents
  Codex started on its own, often go unnoticed, so treat them as unconfirmed until the transcript of
  the estimating chat shows them, and record the item as the kind the transcript shows. When no
  unused chat of the kind wanted next exists, or that kind has to be present for certain, use
  `a-estimate-scratch-log` for that kind instead. For the session 7 lab chat, the learner was asked
  to note their Toolkit spend before and after, so the estimate can be set beside a real change in
  spend for that stretch; whether the Toolkit page updates finely enough to show one lab session's
  spend has not been checked. If they did not note it, or the page does not show the change, the lab
  chat is estimated like any other, with nothing to set beside it. Hold fixed: the chat was finished
  before the estimate is asked for; the request is made in a new chat; the learner does no
  arithmetic; prices come from U-M's pricing page, and if the agent says it read the page, the
  learner checks the rows it used against the page in their browser. For a learner on their own
  ChatGPT subscription the instance is the same, except that nothing is billed per token, so the
  question is what the chat would have cost on a Toolkit key, and why that differs from what they
  paid is part of the answer.
- **worked example:** at the first level of help, show one request that works: "Find the Codex
  session log for my chat on [day] about [topic] (under ~/.codex/sessions, or
  ~/.codex/archived_sessions if I archived it). Without reading the whole file into this chat,
  pull out which model it used and its token counts, then estimate the cost with the prices I paste
  from U-M's pricing page. Tell me which counts and which prices you used." At the next level, say in
  one sentence what to check in the reply: whether it added up running totals, and whether the log
  showed more than one model.
- **doesn't show:** the tutor can check the basis against the transcript but cannot check the figure
  against a bill, because the Toolkit page shows spend per key and not per chat; only the session 7
  lab run comes near, if spend was noted and the page shows the change, and any other use of the key
  in that stretch blurs it. The ruling is on reporting the agent's basis accurately, so a pass does
  not show the learner would catch a wrong basis (running totals added up, reasoning tokens counted
  twice), which the study activities spend most of their effort on. Nor does it show they would
  catch a basis that looks right and is not: the last token_count event's running total is not the
  chat's total in a chat that overran its context window, where Codex resets the running total so
  later ones undercount what came before (the bank's compacted chat may be one), or in a forked
  chat, whose running total includes its parent's usage. A first run on a single-model
  chat with no subagents leaves most reasons for a difference unexercised; only later runs reach a
  model switch or subagents. It depends on the agent reaching the learner's session
  logs, which has not been checked on Windows or from inside every project. And since the tutor
  asks for a chat to estimate, it does not show the learner would think to ask at all.
- **offer as:** the real thing, on your own work, which is what you will be doing before you say what
  your app cost at the session 8 demo. Each later run picks a harder chat. It needs a finished chat
  worth estimating and an agent that can reach your session logs.
- **check note:** The chat used in `a-watch-estimate-narrated` is not recorded in any label and is a
  likely first item here, so ask the learner which chat that was and do not serve it. An attempt
  stopped because the agent could not reach the log is still logged, with criterion unchecked; "not
  counted as a miss" does not mean left out of the log. The entry never says who gives the agent
  U-M's rows, and a request without them may be priced from the agent's memory of a vendor list;
  that is a wrong basis, ruled as the entry already rules one. The entry gives the judge no standard
  for why the figure may differ: hand over the one in `a-estimate-scratch-log` (specific reasons
  that fit this chat and this key). Agents often add caveats of their own about the bill, and the
  learner may ask for more. Tell the judge which of the learner's reasons first appeared in the
  agent's replies, so it can weigh whether the learner could give them without the agent.

### `a-estimate-scratch-log`

- **serves:** `c-ask-cost-estimate`
- **supports:** attempt
- **checks:** `c-ask-cost-estimate`
- **artifact:** no external source. A small invented session log the tutor builds per the generator
  below, in a scratch folder outside any repository; the learner's own Codex agent; and U-M's
  pricing page, https://its.umich.edu/computing/ai/pricing, one table of each model's prompt and
  completion rates per 1M tokens, which the learner opens in a browser, since an agent asked to read
  it is refused (the tutor reads it through the rows the learner pastes; see `tutor does`). 20
  minutes.
- **verified:** 2026-09-17 for the Codex session log format, against the openai/codex source. U-M's
  pricing page 2026-09-17, read in a browser by the instructor: it lists gpt-5.6-sol, gpt-5.6-terra,
  gpt-5.6-luna and gpt-5-mini, with prompt and completion rates per 1M tokens only and no
  cached-input or cache-write rate.
- **learner does:** opens Codex on the scratch folder, starts a new chat, and asks the agent in their
  own words to estimate what the chat recorded in that folder cost. Reads the reply and asks until it
  says what the figure rests on. Then, without help, tells the tutor which model's prices and which
  token counts the figure used, and why it may differ from what was billed, including, at Medium and
  Hard, the billed figure the tutor supplies. Keeps the transcript of the estimating chat.
- **tutor role:** none
- **tutor does:** builds the log files before the session (if it cannot write outside the
  learning-topics repository, it gives the learner the files to save in the scratch folder, asking
  them to save without reading). At Medium and Hard, opens the session by having the learner open
  U-M's pricing page in a browser and paste the rows for the models in the log, unless they already
  pasted them earlier in this sitting, and only then sets the billed figure from those rows. Writes
  down, out of the learner's sight, what the log contains: models, any switch, cached input, any
  subagent file, and any supplied spend figure with the cause of its difference. Waits during the
  attempt. Afterwards keeps the transcript, that list and the learner's explanation verbatim for the
  judge, then tells the learner what the log contained. Tells the judge two things. Naming the
  planted cause of the billed difference is not required: specific reasons that fit this log and
  this key meet the criterion whether or not they include it. And if the agent's basis was itself
  wrong (it added up the running totals, or added reasoning tokens on top of output), a learner who
  reports it accurately still meets that part of the criterion, since catching a wrong basis is not
  part of it; the tutor points out the error to the learner after the ruling.
- **done when:** criterion met with no help.
- **kind:** generator
- **generator:** inside the scratch folder, make folders laid out like ~/.codex/sessions/YYYY/MM/DD/
  and write one JSONL file named like a real log (rollout-<date>T<time>-<id>.jsonl). Model its lines
  on what Codex wrote on one Mac in September 2026: a session_meta line (id, session_id,
  model_provider "toolkit"); a turn_context line with model and effort; and, for each call to the
  model, an event_msg line whose payload has type token_count and an info object holding
  total_token_usage (the running total for the chat) and last_token_usage (this call), each with
  input_tokens, cached_input_tokens, cache_write_input_tokens, output_tokens,
  reasoning_output_tokens and total_tokens. No message text is needed. Keep the numbers consistent:
  cached and cache-write counts sit inside input_tokens, reasoning inside output_tokens,
  total_tokens is input plus output, and each running total is the previous one plus this call.
  Generate the lines with a short script rather than writing them by hand, so every running total is
  computed and not typed; without a script, keep to 6 to 12 calls. Vary the number of calls (6 to
  40), the input per call (10,000 to 60,000, growing through the chat), the model or models, and how
  many calls show cached input. Easy: one model (gpt-5.6-luna at medium), no cached input, nothing
  else in the folder. Medium: a second turn_context line partway through switching to gpt-5.6-sol,
  some calls with cached input, and a billed figure given as the change in spend on the learner's
  Toolkit key over that hour, set, from the pasted rows, somewhat above a correct estimate because
  another chat also ran in that hour (tell the learner only the figure and that it comes from the
  Toolkit page; whether the page shows spend finely enough to read one hour's change has not been
  checked). Hard: as Medium, plus a second log file in the same day's folder carrying the same
  session_id, a parent_thread_id, a source marking it as a subagent, and its own model and counts,
  with the billed figure including it. Hold fixed: the learner does no arithmetic; prices come from
  U-M's pricing page; the file is plausible enough that an agent treats it as a Codex log; nothing
  in it hints at what to look for. Only a log at Medium or Hard can finish the goal; Easy is for
  practice and for the demonstration in `a-watch-estimate-narrated`.
- **worked example:** show the request from `a-estimate-own-chat`'s worked example, pointed at the
  scratch folder instead of a day and topic. At the next level, ask only: did the agent say which
  model it priced, and did the log have more than one?
- **doesn't show:** the log is invented, so a pass does not show the learner can find their own chat's
  log or that their agent can reach it, and the billed figure is handed to them rather than looked
  up. The subagent file at Hard is modeled on a single observation of a reviewer subagent that Codex
  started on its own; whether subagents a learner asks for are logged the same way has not been
  checked, so a pass at Hard shows they would look for such files, not that such files always exist.
  Where the learner saved the files themselves, the models, the switch and the subagent file may
  have passed in front of them, so at Hard the subagent file is handed over rather than found. The
  planted cause of the billed difference cannot be found from anything the learner has, so a pass
  does not show they would track down the actual cause, only name specific possible ones. The ruling
  is on reporting the agent's basis accurately, so a pass does not show the learner would catch a
  wrong basis.
- **offer as:** the controlled version: none of your own chat history involved, no question of
  whether your agent can reach your logs, and the tutor can put a model switch or a subagent into the
  chat on purpose. Take it when you have no finished chat worth estimating, or when you want the
  harder cases before they have happened in your own work.
- **check note:** Agents often add caveats of their own about why a bill could differ, and at Medium
  and Hard the learner may give the agent the billed figure and ask why. Tell the judge which of the
  learner's reasons first appeared in the agent's replies, so it can weigh whether the learner could
  give them without the agent.

### `a-w-token`

- **origin:** generated
- **serves:** `w-token`
- **checks:** `w-token`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-input-tokens`

- **origin:** generated
- **serves:** `w-input-tokens`
- **checks:** `w-input-tokens`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-output-tokens`

- **origin:** generated
- **serves:** `w-output-tokens`
- **checks:** `w-output-tokens`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-prompt-caching`

- **origin:** generated
- **serves:** `w-prompt-caching`
- **checks:** `w-prompt-caching`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-model`

- **origin:** generated
- **serves:** `w-model`
- **checks:** `w-model`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-reasoning-effort`

- **origin:** generated
- **serves:** `w-reasoning-effort`
- **checks:** `w-reasoning-effort`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-context`

- **origin:** generated
- **serves:** `w-context`
- **checks:** `w-context`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-context-window`

- **origin:** generated
- **serves:** `w-context-window`
- **checks:** `w-context-window`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-compaction`

- **origin:** generated
- **serves:** `w-compaction`
- **checks:** `w-compaction`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's

### `a-w-system-prompt`

- **origin:** generated
- **serves:** `w-system-prompt`
- **checks:** `w-system-prompt`
- **learner does:** whatever the goal's supply instantiates (see
  workflows/learn/skills/goal-setting/references/vocabulary-moves.md)
- **offer as:** the only candidate; which move gets set is the supply's, not this entry's
