# Rubric: failing test

### q-define-failing-test

- **type:** free
- **goal:** w-failing-test
- **move:** DEFINE
- **answer:** a test that ran and did not get what it was looking for: the check it makes did not
  hold, so it reports failure. That is a verdict about the code the test is aimed at, saying the
  app does not do that thing, at least not yet. It does not mean the test itself is faulty, and
  when the work is done test-first it is the expected state before the code is written.
- **credit:** full credit for "the test ran and the thing it checked did not come out the way the
  test required", or the plainer "the code did not pass the check that test makes". "It means the
  app is broken" is also full credit, since it puts the verdict on the app rather than the test.
  Half credit for "a test that didn't pass" with nothing about what that says. No credit for "a red
  test", which is another name for the same thing. No credit for defining it as a test that is
  itself wrong or broken.

### q-failing-vs-broken-test

- **type:** free
- **goal:** w-failing-test
- **move:** DISTINGUISH
- **answer:** a failing test is doing its job: it ran, made its check, and the check did not hold,
  which tells you something about the code being tested. A broken test is one where the fault is in
  the test itself, for instance it looks for a button that has been renamed, so its verdict tells
  you nothing about whether the app works. The fix for a failing test is usually in the app; the
  fix for a broken test is in the test.
- **credit:** full credit for locating the fault: a failing test reports on the code under test,
  while a broken test is itself at fault and its result says nothing about the app. "One means the
  app is wrong, the other means the test is wrong" is full credit, as is the fix-the-app versus
  fix-the-test version. Half credit for "a broken test is worse" or "a broken test won't run", with
  nothing about where the fault lies. No credit for treating them as the same thing, and no credit
  for an answer in which a failing test means something has gone wrong in the process, since in
  test-first work the failure is expected.

### q-red-before-code

- **type:** free
- **goal:** w-failing-test
- **move:** INTERPRET
- **answer:** the test it has just written for saving is failing, and that is deliberate: nothing in
  the app saves a note yet, so the test cannot pass. Seeing it fail first is the evidence that the
  test really does check saving, so when it passes later that will be because the saving code made
  it pass. It rules out reading the failure as something having gone wrong.
- **credit:** full credit for both halves: the test is failing right now, and the failure is wanted
  because the code it tests has not been written. The evidence it buys, that the test is known to
  be able to fail, is a strong addition and is not required. Half credit for "the test is failing"
  with nothing about why that is where the agent wants it. No credit for reading "red" as the test being faulty, the agent being stuck, or the agent asking for help.
