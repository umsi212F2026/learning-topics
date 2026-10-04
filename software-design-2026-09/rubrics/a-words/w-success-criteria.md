# Rubric: success criteria

### q-define-success-criteria

- **type:** free
- **goal:** w-success-criteria
- **move:** DEFINE
- **answer:** the statements in the spec that settle what will count as the app being done and
  doing its job, written so that someone who never heard the idea could use the finished app and
  say of each criterion whether it was met. They are what "finished" gets judged against, rather than a
  list of the parts the app will have.
- **credit:** full credit for saying they are what counts as the app being done, or what has to be
  true of the finished app, settled in advance. Full credit also for an answer that leads with
  their being checkable by someone using the app. Do not accept just another name for them, such as
  "acceptance criteria". Do not accept the tests, or a list of the app's features. Half credit for
  "what the app has to do" with nothing about settling when it is done or about anyone being able
  to check.

### q-criteria-vs-tests

- **type:** free
- **goal:** w-success-criteria
- **move:** DISTINGUISH
- **answer:** success criteria are agreed with you in ordinary words before anything is built, and
  they say what has to be true of the finished app for it to be doing its job, so that anyone
  using it could settle them. Tests are code the agent writes and runs against what it has built,
  checking that the pieces behave the way the code expects. An app can pass every test and still
  fail its success criteria, because the tests only check what somebody thought to write down as
  code.
- **credit:** full credit for both sides: criteria are agreed up front, in words, about what the
  finished app must be true of, and tests are code run against the build. Full credit also for an
  answer that makes the point with passing tests not meaning the criteria are met. Half credit for
  "criteria are in English and tests are code" with nothing about what each is for. Do not accept
  that they are the same thing said twice, that criteria are just vaguer tests, or that tests come
  first.

### q-criteria-are-features

- **type:** free
- **goal:** w-success-criteria
- **move:** CATCH
- **answer:** those are the parts the app will have, a feature list, not statements about what the
  finished app has to be true of. All three could be built and the app could still fail to tell
  anybody whether they know what YAGNI stands for: the Check button could accept anything typed,
  or nothing at all. A criterion says what someone using the app would find: that a person who
  types the right five words is told they are right, and a person who types something else is told
  they are wrong.
- **credit:** full credit for naming them as features or parts rather than statements of what the
  finished app must do, or for showing that an app with all three could still miss what the app is
  for. Half credit for saying they do not say what counts as done, without saying they are
  features. Do not accept a different quibble as the error: that there should be more of them,
  that they are too short, that they say nothing about how the app looks, or that they do not
  mention React.
