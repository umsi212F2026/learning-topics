# Activities: defensive measures

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

This topic is words and an orientation by decision (`**capabilities:** none` in goals.md), so
it holds only these two entries. The minimum route, the orientation and one passed question for
each of the four words, comes to about 25 minutes: about 13 for `a-read-defensive-measures` and
about 3 a word.

## Check notes

## Goals

| id | Goal | Criterion: what gets examined, and what counts |
| -- | ---- | ---------------------------------------------- |
| `o-orientation` | get the shape of this area before working on any particular part of it | `orientation` |

## Coverage

| goal | checks | notes |
| ---- | ------ | ----- |
| `o-orientation` | `a-read-defensive-measures` | |

---

## Activities

### `a-read-defensive-measures`

- **serves:** `all`
- **supports:** orient
- **checks:** `o-orientation`
- **artifact:** a reading the course wrote for this topic, `tasks/read-defensive-measures.md` in
  this folder, "After it's live: four defenses against common problems" (about 710 words, about 5
  minutes). No external reading is used: the instructor looked and none fit. It uses one
  made-up app, Swapboard, a textbook-swap app that has recently gone live. An opening paragraph
  says that its visitors are now strangers, some of them programs and some malicious, and that
  what follows are defenses an agent working on a live app might bring up (or might not), which
  the learner should be prepared to make decisions about. Then it gives one short section to each
  defense, each its own scenario: a script flooding the sign-up address (rate limit), a
  five-megabyte "title" sent straight to the server by a bot that skipped the form (input
  validation), an error recorded in a log nobody read (alert), and a table of books emptied by a
  bad code update (backup). A closing section, Before and after, names two defenses that come before going
  live (secrets out of the repository, and what a visitor who isn't signed in may do) and says
  the deploy-config and sign-in-and-permissions topics cover them. About 5 minutes of reading, 11
  or 12 with the two stops, 12 or 13 with the close (up to 17 if a section is gone over again at
  the close). Words in place: all four words, each in bold where it is introduced, with every synonym
  goals.md lists (throttling, server-side validation, alerting, snapshot, database backup), the
  name for putting a backup back (restoring, also in bold), the name for the line an alert
  watches (threshold, also in bold) and every nearest
  confusable (overage, the check in the browser's form, the server log, a host's health check,
  rollback, git history). The reading names no real host or service.
- **learner does:** reads the page once, top to bottom, and stops twice, answering before reading
  on; "I don't know yet" is an honest answer.
  1. After Input validation: says what the sign-up flood and the five-megabyte title each looked
     like to the server (many ordinary requests; one request that wasn't what it expected), and
     why each section's defense would have done nothing about the other section's trouble.
  2. After Backup: sorts the four defenses by when each one does its work: keeping the trouble
     out before it does damage, telling someone while it is going on, or getting the app back
     afterwards; and says which of the reading's four scenarios nothing but the last of these
     could have undone.
  Then the close, about 1 minute (up to 5 if a section is gone over again), with the reading
  still beside them: answers the question the tutor puts: with this page beside you, could you
  now follow a conversation with your agent or a classmate about these four defenses (rate limit,
  input validation, alert and backup): know which one is meant when it is proposed, ask for one
  by name, and notice when one is being mixed up with something nearby, such as a rollback taken
  for a backup?
- **tutor role:** explainer
- **tutor does:** puts the reading in front of the learner by opening the file
  `tasks/read-defensive-measures.md` from the topic folder on the local filesystem, so the
  learner's agent shows it formatted in a sidebar; does not paste it into the chat. Stays quiet
  through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you said the rate limit would have stopped the five-megabyte title; how many requests
  did that bot send?"). Stop 2's intended sort is rate limit and input validation keeping
  trouble out, alert telling someone, and backup getting the app back, with the emptied books
  table as the scenario only a backup undoes; a learner who puts the alert with the defenses that keep
  trouble out gets one near-miss question ("if Swapboard had had an alert when the log errors started, would it have stopped the page crashing?")
  and the sort is not ruled on. Does not set or rehearse any word question from `a-words`: does
  not ask the learner to define a word, does not put a word against one of its confusables
  (overage, the browser's form check, the server log, a health check, rollback, git history), and
  does not offer a misused sentence to correct; the stops are about the reading's scenarios, and if the
  learner raises a confusable, the tutor points to the paragraph that mentions it and leaves it
  there. Says that setting any of these up, and choosing the numbers (how many requests a minute,
  how many errors before an alert, how often a backup), are past this topic's depth, and that
  the two defenses in Before and after belong to deploy-config and sign-in-and-permissions;
  reading a deployed app's logs and putting the last working deploy back belong to
  debug-deployed. At the close, puts the readiness question as written above and rules on the
  answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops
  or on whether the tutor thinks they are ready. A plain yes is `criterion: met`. A hedge on one or
  more of the four defenses, with no plain no, is `criterion: unclear`: go over that defense's
  section of the reading once more and put the question again; a second hedge stays `unclear`,
  and the tutor offers that word's question from `a-words`. A hedge on one of the three abilities
  rather than on a defense ("I'd know them, but I'm not sure I'd catch a mix-up"), with no plain
  no, is also `criterion: unclear`. The tutor asks which defense the doubt is about; if it names
  one, that defense's section is gone over once more, as above. If it doesn't, then for knowing
  which is meant or asking by name the learner rereads the four bolded definitions, and for
  noticing a mix-up the tutor points to the paragraphs where the reading sets each defense beside
  its neighbor (the overage, the form's check, the log and the health check, the rollback and git
  history) without quizzing on them; then the question is put again. A second hedge stays
  `unclear`, and the tutor offers the questions from `a-words`, since telling a word from its
  nearest confusable is what those check. A plain no is `criterion: not met`:
  record it, ask what is missing, and offer to go back over the stop or the section that bears on
  it; don't put the question again in the same sitting. This goal isn't required, so a no never
  blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the four words, which have their own supply in `a-words`: there is no
  rehearsal of their questions, by design, and the stops are helped and ungraded. In particular
  it doesn't show that the learner can notice a mix-up, whether between two of the defenses or
  between a defense and something nearby: the readiness question asks only whether they think
  they could, and noticing a word mixed up with its nearest confusable is what `a-words` checks.
  The reading is
  one course-written page about one made-up app, so it shows nothing of how a real host or
  library names or offers these defenses, or how an agent's own words for them may differ; it
  carries only the synonyms goals.md lists (one each for three of the words, two for backup) and no more.
- **offer as:** this topic's orientation, and its only activity besides the words: one short page
  the course wrote, about one made-up app just after it goes live, in which each of four short
  scenarios introduces one of the four defenses, with two short stops and a one-question close. About 13
  minutes, a few more if a section is gone over again at the close.
- **check note:** Make the remark about depth at the close, just before you put the readiness
  question: setting any of these up and choosing the numbers are past this topic, the two
  defenses in Before and after belong to deploy-config and sign-in-and-permissions, and reading
  a deployed app's logs and putting the last working deploy back belong to debug-deployed. The
  reading itself gives a number only as an example (twenty a minute, three errors in an hour), so
  if the learner asks what the right number is, say that choosing it is past this topic rather
  than answering. At Stop 2 a learner may argue that input validation could have kept out
  the crash recorded in the unread log; that doesn't change the sort, so let it stand and go on.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
