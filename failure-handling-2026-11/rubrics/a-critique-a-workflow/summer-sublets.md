Four steps and one check. The collecting program adds an entry for each new listing and says nothing when a page won't open, adding no entry. The assessing agent writes each listing's rating into its entry, overwriting any rating already there, with no test for done. The extracting program passes over any listing that already has a details file, a test a partly written file passes, and puts any listing with no rent on the problems list. The flagging program looks only for entries with no rating, and reports at the top of the sublets list. The viewing program, at noon, posts each 'worth a look' listing collected the night before to a board Callum shares with two friends, with no test for done; the board is outside the workflow, and other people read it. Callum's routine each morning is the problems list, then the entries at the top of the sublets list, then the details file of each 'worth a look' listing; nothing in it takes him to a saved page or to the details file of a 'skip' listing. The three rerun questions carry `replaces-used`, `half-written` and `duplicates`; `already-safe` is left for one quick-check question. The collecting program gets no rerun question.

### rerun-assessing

- **goal:** `c-judge-rerunnable`
- **cases:** replaces-used
- **type:** mcq
- **answer:** 5
- **credit:** full for 5 only.
- **tutor note:** Hard, shape `redoes-acted-on`, with a later step acting on results. Settled by "writes into that listing's entry a rating of 'worth a look' or 'skip' ... overwriting any rating already there", with nothing said about passing over listings already rated, so the agent passes over nothing: a rerun rates all 20 listings afresh, the agent may judge one of the first 11 differently when asked a second time, and the new rating overwrites one the viewing program has already acted on, so the posts already on the board no longer agree with the ratings. Not 1, because an agent that rewrites every rating with no test for done is not idempotent, whatever it happens to answer this time. Not 2, because each listing keeps one entry and one rating. Not 3, because the agent writes only into entries; the posts came from the viewing program, which is not being run. Not 4, because the stop came between listings, and the rerun rewrites every listing anyway.

### rerun-extracting

- **goal:** `c-judge-rerunnable`
- **cases:** half-written
- **type:** mcq
- **answer:** 4
- **credit:** full for 4 only.
- **tutor note:** Medium, shape `trusts-partial`. Settled by "It passes over any listing that already has a details file" with the stop while writing the 8th listing's details file: that file holds only part of the rent and dates, and the rerun passes over it because the file exists. Not 1, because of the 8th listing. Not 2, because listings 1 to 7 have details files and are passed over, and each listing has its own file. Not 3, because the program writes only details files and the problems list, both inside the tracker. Not 5, because finished listings are passed over and nobody has opened any details files.

### rerun-viewing

- **goal:** `c-judge-rerunnable`
- **cases:** duplicates
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** Medium, shape `acts-again`. Settled by "for each one rated 'worth a look' it posts the listing to the house-hunting board Callum shares with the two friends he will live with", with nothing said about passing over listings already posted, so the program passes over nothing: a rerun goes through the same listings and posts the first two to the board a second time, where his friends see them. Not 1, because of those second posts. Not 2, because the program adds nothing to any kept thing in the tracker; the board is outside it, and other people read it. Not 4, because the stop came between listings. Not 5, because nothing in the tracker is rewritten.

### detect-collecting

- **goal:** `c-judge-detection`
- **cases:** unheard
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only.
- **tutor note:** Hard, shape `unheard`, variant `goes-on-quietly`, with a check present. Settled by "When a listing's page won't open, the program says nothing and goes on to the next listing, adding no entry for it": the program could tell the page didn't open, but told no one. The flagging program looks only at entries with no rating, and the listing has no entry at all, so it gives the flagging program nothing to flag. The collecting program writes nothing to the problems list, and Callum's routine covers only the problems list and entries that exist. Not 1, because neither the flag nor his routine reaches a listing with no entry. Not 3, because the program could tell something went wrong. A learner who picks 1 because a flagging program exists should be asked what it would find for this listing.

### detect-assessing

- **goal:** `c-judge-detection`
- **cases:** looks-right
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only.
- **tutor note:** Hard, shape `looks-right`, close to `check-elsewhere` and `review-elsewhere` at once. Settled by the result: 'skip' is a plausible rating, and the agent has no way to tell it is wrong. The flagging program looks only for entries with no rating, and this entry has one. Callum reads only the entries the flagging program put at the top and the details files of 'worth a look' listings, so he never opens this listing's details file or its page. The viewing program posts only 'worth a look' listings, so it passes over this one. Not 1, because nothing in the workflow looks at a rated 'skip' listing. Not 2, because the agent could not tell anything went wrong.

### detect-extracting

- **goal:** `c-judge-detection`
- **cases:** detected
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Hard, shape `heard`, variant `listed`. Settled by "When it finds no rent on a page, it adds the listing to the problems list and goes on" with "Each morning Callum reads the problems list": the program could tell it found no rent, and it says so in the first place Callum reads each morning. Not 2, because the problems list is part of his routine. Not 3, because there is no plausible wrong result here, only a missing rent that the program reports. A learner who picks 2 because the program goes on to the next listing should be asked where it said so and whether Callum reads that.
