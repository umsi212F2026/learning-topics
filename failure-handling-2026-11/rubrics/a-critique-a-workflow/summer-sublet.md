Three steps and one check. The collecting program adds a line for every listing posted since the day began, with no test for done, and reports a site that doesn't answer only in a problems file Priya never opens. The assessing agent writes a notes file per listing and passes over any listing that already has one, a test a partly written file passes; when it can't open a page it writes no notes file. The extracting program writes each line's fields in place from saved pages that never change. The counting program compares the assessing agent's own output, notes files, with the saved pages, which that agent didn't make, and reports at the top of the list Priya reads each evening. Priya's review covers only listings rated 'worth a look'.

### q1

- **goal:** `c-judge-rerunnable`
- **cases:** duplicates
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by "adds a line for it to the listings list; it pays no attention to what the list holds already" together with "takes every listing ... posted since the day began": the rerun takes listings 1 to 18 a second time and adds a second line for each. Not 1, because of those lines. Not 3, because the stop came just after the 18th was saved and its line added, between listings. Not 4, because adding leaves the first 18 lines as they were and nobody has opened the list. Medium: no test for done, said plainly.

### q2

- **goal:** `c-judge-rerunnable`
- **cases:** half-written
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "It passes over any listing that already has a notes file" and the stop while writing the 12th: that file exists but holds only part of its notes, so the rerun passes over it, and the 12th listing is left without a full rating. Not 1, because of the 12th. Not 2, because listings 1 to 11 have notes files and are passed over, and each listing has one file. Not 4, because finished listings are passed over and nobody has opened any notes. Medium: the test a partial file passes is said plainly. If a learner says the counting program would flag it, point out that it counts files, and the 12th has one.

### q3

- **goal:** `c-judge-rerunnable`
- **cases:** already-safe
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for the others.
- **tutor note:** settled by "Nothing changes a saved page after it is saved" and "writes them into that listing's line, over whatever is there": a program working from pages that never change writes the same address, rent and contact it wrote before, so the 40 lines Priya read and acted on stay as they were. Not 2, since it writes into each listing's existing line rather than adding. Not 3, since the stop came between lines and the rerun rewrites every line anyway. Not 4, since the result written is the same. Hard: Priya has acted on the results, which pulls toward 4. A learner choosing 4 is usually thinking of the assessing agent, which could judge differently; this step is a program reading unchanged pages.

### q4

- **goal:** `c-judge-detection`
- **cases:** unheard
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only; none for the others.
- **tutor note:** settled by "If a site doesn't answer, the collecting program writes a line about it in a problems file, in a folder Priya never opens": the step can tell, but says so only where nobody looks. Not 3, because the step knows the site didn't answer. Not 1: the counting program compares notes files with saved pages, and nothing was saved from that site, so the numbers still match; Priya reads the list and the 'worth a look' notes, which show only listings that were saved, and nothing in either says a site is absent. Medium: no check or review looks at which sites answered.

### q5

- **goal:** `c-judge-detection`
- **cases:** detected
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only; none for the others.
- **tutor note:** settled by "if it can't open a saved page, it goes on to the next one without writing anything" together with the counting program: the page was saved but gets no notes file, so there is one fewer notes file than saved pages, and the counting program puts a line saying one is missing at the top of the list Priya reads each evening. Not 2, because the shortfall reaches her even though the agent itself says nothing. Not 3, because there is no wrong result to look right; there is a missing one, and the count is aimed at exactly that. Hard: the agent itself says nothing, and the learner must see that the count covers its output.

### q6

- **goal:** `c-judge-detection`
- **cases:** looks-right
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only; none for the others.
- **tutor note:** settled by "reads the notes for every listing rated 'worth a look'": a 'skip' rating is a plausible result, and Priya never reads the 'skip' notes. Not 2, because the agent has no way to tell its rating is wrong. Not 1: the counting program looks only at how many notes files there are, and this listing has one; Priya's review covers only 'worth a look' listings. Hard: both a check and a review are in the workflow, each looking at something other than this mistake.
