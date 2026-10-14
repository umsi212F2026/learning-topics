# Activities: defensive measures

Candidate activities for the study phase. More than will be used; the tutor chooses among them
with the learner.

This topic is words and an orientation by decision (`**capabilities:** none` in goals.md), so
it holds only these two entries. The minimum route, the orientation and one passed question for
each of the four words, comes to about 30 minutes: about 18 for `a-read-defensive-measures` and
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
  this folder, "After it's live: four defences" (about 650 words, 4 to 5 minutes). No external
  reading is used: the instructor looked and none fitted. It follows one made-up app, Swapboard, a
  textbook-swap app that has just gone live, through one week in which a different thing goes
  wrong each day, and gives one short section to each defence: a sign-up flood on Tuesday (rate
  limit), a five-megabyte "title" sent straight to the server on Wednesday (input validation), an
  error in a log nobody read on Thursday (alert), and a table of books emptied by a bad change on
  Friday (backup). A closing section, Before and after, names two defences that come before going
  live (secrets out of the repository, and what a visitor who isn't signed in may do) and leaves
  them to other topics. About 5 minutes of reading, 11 or 12 with the two stops, 17 or 18 with the
  close. Words in place: all four words, each in bold where it is introduced, with every synonym
  goals.md lists (throttling, server-side validation, alerting, snapshot) and every nearest
  confusable (overage, the check in the browser's form, the server log, a host's health check,
  rollback, git history). The reading names no real host or service.
- **learner does:** reads the page once, top to bottom, and stops twice, answering before reading
  on; "I don't know yet" is an honest answer.
  1. After Input validation: says what Tuesday's trouble and Wednesday's trouble each looked like
     to the server (many ordinary requests; one request that wasn't what it expected), and why
     each day's defence would have done nothing about the other day's trouble.
  2. After Backup: sorts the four defences by when in the week's trouble each one does its work:
     keeping the trouble out before it does damage, telling someone while it is going on, or
     getting the app back afterwards; and says which day's trouble, in the reading, nothing but
     the last of these could have undone.
  Then the close, about 5 minutes, with the reading still beside them: answers the question the
  tutor puts: with this page beside you, could you now follow a conversation with your agent or a
  classmate about these four defences (rate limit, input validation, alert and backup): know
  which one is meant when it is proposed, ask for one by name, and notice when two of them are
  being mixed up?
- **tutor role:** explainer
- **tutor does:** stays quiet through the reading except at the stops and when asked. At each
  stop, takes the learner's answer first and replies with one near-miss question rather than a
  verdict ("you said the rate limit would have stopped Wednesday's request; how many requests did
  Wednesday's visitor send?"). Stop 2's intended sort is rate limit and input validation keeping
  trouble out, alert telling someone, and backup getting the app back, with Friday's emptied table
  as the day only a backup undoes; a learner who puts the alert with the defences that keep
  trouble out gets one near-miss question ("on Thursday, did the alert stop the page crashing?")
  and the sort is not ruled on. Does not set or rehearse any word question from `a-words`: does
  not ask the learner to define a word, does not put a word against one of its confusables
  (overage, the browser's form check, the server log, a health check, rollback, git history), and
  does not offer a misused sentence to correct; the stops are about the week's story, and if the
  learner raises a confusable, the tutor points to the paragraph that mentions it and leaves it
  there. Says that setting any of these up, and choosing the numbers (how many requests a minute,
  how many errors before an alert, how often a backup), are past this topic's depth, and that
  the two defences in Before and after belong to deploy-config and sign-in-and-permissions;
  reading a deployed app's logs and putting the last working deploy back belong to
  debug-deployed. At the close, puts the readiness question as written above and rules on the
  answer.
- **done when:** criterion met. The bar for this goal is did it once and help is expected
  throughout, so the ruling is on the learner's answer to the readiness question, not on the stops
  or on whether the tutor thinks they are ready. A plain yes is `criterion: met`. A hedge on one or
  more of the four defences, with no plain no, is `criterion: unclear`: go over that defence's
  section of the reading once more and put the question again; a second hedge stays `unclear`,
  and the tutor offers that word's question from `a-words`. A plain no is `criterion: not met`:
  record it, ask what is missing, and offer to go back over the stop or the section that bears on
  it; don't put the question again in the same sitting. This goal isn't required, so a no never
  blocks anything else the learner wants to try.
- **worked example:** n/a
- **doesn't show:** an indication of readiness is all this goal asks for and all this shows. It
  shows nothing about the four words, which have their own supply in `a-words`: there is no
  rehearsal of their questions, by design, and the stops are helped and ungraded. The reading is
  one course-written page about one made-up app, so it shows nothing of how a real host or
  library names or offers these defences, or how an agent's own words for them may differ; it
  carries one synonym for each word and no more.
- **offer as:** this topic's orientation, and its only activity besides the words: one short page
  the course wrote, following one made-up app through a week in which each day's trouble
  introduces one of the four defences, with two short stops and a one-question close. About 18
  minutes.

### `a-words`

- **serves:** group vocabulary
- **generator:** the five moves in `workflows/learn/skills/goal-setting/references/vocabulary-moves.md`, set for one word at a time from its `what it names`, `nearest confusable` and `synonyms`. Each question names that word's goal and carries its move.
- **learner does:** answers one short question about one word
- **tutor role:** examiner
- **tutor does:** sets the question as served, without rewording it or hinting; when the bank has nothing for the word, sets one move live, as vocabulary-moves.md describes
- **offer as:** not offered as a choice; a word's question is set when that word is studied or due
