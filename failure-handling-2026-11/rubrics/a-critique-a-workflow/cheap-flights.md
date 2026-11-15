Three steps and one check. The collecting program adds an entry for every deal it finds, with no test for done, and writes trouble only to a problems file. The assessing agent passes over any deal with a notes file, a test a partly written file passes, and says nothing when it can't open a page. The extracting program writes fields in place from saved pages that never change, so it writes the same values each time. The counting program compares the assessing agent's notes files with the entries in the deals list, which the agent didn't make, and reports at the top of the list. Owen's routine is the deals list from the top, then the notes, fare and airline of each 'worth a look' deal; nothing in it takes him to the problems file or to a saved page. The three rerun questions carry `duplicates`, `half-written` and `already-safe`; `replaces-used` is left for one quick-check question.

### rerun-collecting

- **goal:** `c-judge-rerunnable`
- **cases:** duplicates
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** Medium, shape `adds-again`. Settled by "It adds an entry for every deal it finds, even if the list already has one for that deal": a rerun goes through every newsletter from the past day, so each deal from the first two newsletters gets a second entry. Not 1, because of those entries. Not 3, because the program only saves pages and adds entries, nothing outside the workflow. Not 4, because the stop came between newsletters, not while an entry was being written. Not 5, because adding leaves the first entries as they were, and nobody has opened the list since.

### rerun-assessing

- **goal:** `c-judge-rerunnable`
- **cases:** half-written
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** Medium, shape `trusts-partial`. Settled by "The agent passes over any deal that already has a notes file" with the stop while writing the 9th deal's notes: that file holds only part of its notes, likely with no rating, and the rerun passes over it because the file exists. Not 1, because of the 9th deal. Not 2, because deals 1 to 8 have notes files and are passed over, and each deal has its own file. Not 3, because the agent writes only notes files. Not 5, because finished deals are passed over and nobody has opened any notes.

### rerun-extracting

- **goal:** `c-judge-rerunnable`
- **cases:** already-safe
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Hard, shape `already-safe`, variant `same-inputs`. Settled by "Nothing changes a saved page after it is saved" with "writes them into that deal's fare and airline fields in the deals list, overwriting whatever is there": a program working from the same pages writes the same fares and airlines it wrote before, so the six fares Owen read stay as they were. Not 2, because it writes each deal's own fields rather than adding entries. Not 3, because it does nothing outside the workflow. Not 4, because the stop came between deals, and the rerun rewrites every deal anyway. Not 5, because the values written are the same. A learner who picks 5 because Owen has read results is reading "has been read" as "will change"; ask what the program works from and whether that has changed.

### detect-collecting

- **goal:** `c-judge-detection`
- **cases:** unheard
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** Hard, shape `unheard`, variant `unopened-note`, with a check present. Settled by "the program writes a line saying so to a problems file in the tracker's folder and goes on to the next deal, adding no entry for it": the program could tell the page didn't load and said so, but Owen's routine is the deals list and the notes of 'worth a look' deals, and nothing sends him to the problems file. The counting program compares notes files with entries; the deal has neither an entry nor a saved page, so the agent wrote no notes for it and the two numbers still match. Owen's review covers only deals in the list. Not 1, because neither the count nor the review reaches a deal with no entry. Not 3, because the program could tell something went wrong.

### detect-assessing

- **goal:** `c-judge-detection`
- **cases:** detected
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Hard, shape `heard`, variant `aimed-check`. Settled by the counting program, which compares the number of notes files with the number of entries and puts a line at the top of the deals list when they don't match: the deal has an entry and a saved page but no notes file, so the numbers differ, and Owen reads the list from the top each morning. The agent itself says nothing, which is why a learner may pick 2; ask what the counting program would find. Not 2, because the count brings it to Owen before he reads the deals. Not 3, because there is no plausible wrong result here, only a missing notes file.

### detect-extracting

- **goal:** `c-judge-detection`
- **cases:** looks-right
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** Hard, shape `looks-right`, close to `review-elsewhere` and `check-elsewhere` at once. Settled by the result: $248 is a plausible fare, in the right field, and the program has no way to tell it took the wrong figure. The counting program looks only at how many notes files and entries there are. Owen's review does reach this deal and its fare, but he reads the fare from the list, never beside the saved page, so nothing compares it with the $331 the page gives. Not 1, because neither the count nor the review compares the fare with the page. Not 2, because the program could not tell anything went wrong. A learner who picks 1 because Owen reads the fare is taking any look at a result as a check on it; ask what he would have to look at to see it is wrong.
