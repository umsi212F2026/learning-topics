# Rubric: regression

### q-define-regression

- **type:** free
- **goal:** w-regression
- **move:** DEFINE
- **answer:** something that used to work and does not any more, broken by a change that was just
  made. The app has gone backwards from a state that was good: not a part that was never finished,
  and not a fault that was always there, but working behavior lost.
- **credit:** full credit for both halves: behavior that worked before has stopped working, and a
  change is what caused it. Half credit for "something broke" or "a bug" with no sense of going
  backwards from a working state, and half credit for "the same bug has come back", which is one
  kind of regression and misses the general case. No credit for "any bug in the app", for a problem
  the app always had, or for regression in the statistical sense of a line fitted to data.

### q-regression-vs-new-bug

- **type:** free
- **goal:** w-regression
- **move:** DISTINGUISH
- **answer:** the regression is behavior that used to work and has stopped, so there is a good
  state to go back to and a recent change is the suspect. The new bug is a fault in something new,
  or in something that never worked properly, so nothing has gone backwards: it was just written or
  just found. Only one of the two points at a change to look through.
- **credit:** full credit for the backwards step: a regression is about behavior that worked before
  and does not now, because of a change, while the new bug never worked. Half credit for "one is
  old and one is new" with nothing about having worked before. No credit for a difference of
  severity, of who found it, or of whether a test caught it.

### q-catch-regression-never-worked

- **type:** free
- **goal:** w-regression
- **move:** CATCH
- **answer:** nothing has gone backwards. The ordering never worked, so this is not working
  behavior lost to a change; it is a fault that was there from the first version and has only just
  been noticed. When you noticed it is not what makes something a regression.
- **credit:** full credit for saying a regression needs behavior that worked before and was broken
  by a change, and this behavior never worked. Do not accept a different quibble as the error: that
  they should have tested sooner, that the agent should have caught it, that the word does not
  matter, or that the bug is a small one.
