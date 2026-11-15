Shape `already-safe`, variant `sound-skip`, Hard: the agent's test for done is a 'rated' mark added only after a notes file is written in full, so the stopped run cannot fool it. The 12th lottery has no mark, and the agent overwrites its notes file from the start.

### q1

- **goal:** `c-judge-rerunnable`
- **cases:** already-safe
- **type:** mcq
- **answer:** 1
- **credit:** full for 1 only.
- **tutor note:** Settled by "Once a lottery's notes file is written in full, the agent marks the lottery's entry 'rated'. It passes over any lottery marked 'rated'" together with "overwriting any notes already in it": the first 11 lotteries are marked and passed over, and the 12th, unmarked, gets its notes written whole over the unfinished ones. Not 2: the agent writes each lottery's own notes file and adds no entries. Not 3: the agent does nothing outside the workflow; entering lotteries is Odile's own doing. Not 4: the 12th lottery's unfinished notes have no 'rated' mark, so the rerun rewrites them rather than passing over them. Not 5: the 11 lotteries whose notes Odile read are marked 'rated' and passed over, so their notes stay as they were. A learner who picks 4 has spotted the stop in the middle of writing; ask whether the 12th lottery is marked 'rated'.
