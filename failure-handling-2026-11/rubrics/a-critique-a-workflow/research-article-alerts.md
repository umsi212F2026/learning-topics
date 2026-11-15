Three steps and one check. The collecting program adds an entry for every article it finds and passes over articles on a finished list that it saves only when a run ends, so a stopped run never saves it; when a page won't open it shows a warning in a window that closes when the run ends, at 1 a.m. while Lucia is asleep. The assessing agent writes each article's rating into its entry, overwriting any rating already there, with no test for done. The extracting program writes fields in place and passes over articles marked 'details done', a mark it adds only after all three fields are written, so a stopped run cannot fool it. The flagging program looks only at whether an entry's year field is empty, and reports at the top of the articles list. Lucia's routine is the articles list from the top, then the saved page of every 'read it' article in full; nothing in it takes her to a saved page of a 'skip' article, and the warning window is gone before she opens the laptop. The three rerun questions carry `duplicates`, `replaces-used` and `already-safe`; `half-written` is left for one quick-check question.

### rerun-collecting

- **goal:** `c-judge-rerunnable`
- **cases:** duplicates
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** Hard, shape `adds-again`, with a test for done the stopped run fools. Settled by "It passes over any article on its finished list, which it saves when a run ends": the run stopped before it ended, so the finished list never got the articles from the first alert, and a rerun goes through every alert from the past day and adds a second entry for each of them. Not 1, because of those entries. Not 3, because the program only saves pages and adds entries, nothing outside the workflow. Not 4, because the stop came between alerts, not while an entry was being written. Not 5, because adding leaves the first entries as they were, and nobody has opened the list since. A learner who picks 1 because the program passes over finished articles is taking the test at its word; ask when the finished list gets saved.

### rerun-assessing

- **goal:** `c-judge-rerunnable`
- **cases:** replaces-used
- **type:** mcq
- **answer:** 5
- **credit:** full for 5 only.
- **tutor note:** Medium, shape `redoes-acted-on`, with a person acting on results. Settled by "It writes a rating of 'read it' or 'skip' into that article's entry ... overwriting any rating already there", with nothing said about passing over articles already rated, so the agent passes over nothing: a rerun rates all 16 articles afresh, the agent may judge one of the first ten differently when asked a second time, and the new rating overwrites one Lucia has already read and acted on by starting the four 'read it' articles. Not 1, because an agent that rewrites every rating with no test for done is not idempotent, whatever it happens to answer this time. Not 2, because each article keeps one entry and one rating. Not 3, because the agent writes only into entries, nothing outside the workflow. Not 4, because the stop came between articles, and the rerun rewrites every article anyway.

### rerun-extracting

- **goal:** `c-judge-rerunnable`
- **cases:** already-safe
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Hard, shape `already-safe`, variant `sound-skip`, with the stop in the middle of writing. Settled by "It passes over any article marked 'details done', a mark it adds only after all three fields are written" with "writes them into that article's year, authors and journal fields, overwriting whatever is there": articles 1 to 6 carry the mark and are passed over; the 7th has no mark, since its fields were not all written, so the rerun writes all three of its fields whole, overwriting what was there. Not 2, because it writes each article's own fields rather than adding entries. Not 3, because it does nothing outside the workflow. Not 4, because the 7th article is not passed over, so its partial fields are overwritten rather than trusted. Not 5, because finished articles are passed over, and nobody has opened the list since. A learner who picks 4 because the stop came while writing should be asked whether the rerun passes over the 7th article.

### detect-collecting

- **goal:** `c-judge-detection`
- **cases:** unheard
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** Medium, shape `unheard`, variant `unwatched-window`, with a check present. Settled by "the program shows a warning in a window that closes when the run ends, and goes on to the next article, adding no entry for it", with the run at 1 a.m. while Lucia is asleep: the program could tell the page didn't open and said so, but the window is gone before her afternoon routine. The flagging program looks only at entries whose year field is empty, and the article has no entry at all, so it gives the flagging program nothing to flag. Lucia's review covers only articles in the list. Not 1, because neither the flag nor her review reaches an article with no entry. Not 3, because the program could tell something went wrong.

### detect-assessing

- **goal:** `c-judge-detection`
- **cases:** detected
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Medium, shape `heard`, variant `aimed-review`. Settled by "then opens the saved page of every article rated 'read it' and reads it in full": this article is rated 'read it', so Lucia reads it in full and sees it is about office fans, not trees or streets. The flagging program looks only at empty year fields and has no bearing here. Not 2, because the agent has no way to tell its rating is wrong. Not 3, because Lucia's review reaches exactly this article. A learner who picks 3 because the rating looks plausible should be asked which articles Lucia reads in full.

### detect-extracting

- **goal:** `c-judge-detection`
- **cases:** looks-right
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** Hard, shape `looks-right`, variant `check-elsewhere`. Settled by the result: 2009 is a plausible year, in the right field, and the program has no way to tell it took the wrong figure. The flagging program looks only at whether the year field is empty, and this one isn't. Lucia reads the list from the top, which shows the year but not the page beside it, and she opens the saved pages only of articles rated 'read it', so she never opens this one. Not 1, because neither the flag nor her review compares the year with the page. Not 2, because the program could not tell anything went wrong. A learner who picks 1 because a flagging program exists should be asked what exactly it looks for.
