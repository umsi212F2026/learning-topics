# Rubric: Stochastic

If the learner misses a question here, set a DEFINE or INTERPRET move for stochastic live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A stochastic model has chance built into its rules, so running it again with the same settings can
give a different result. A deterministic model has no chance in its rules and gives the same result
every time it runs with the same settings. "Probabilistic" is another name for stochastic, not a
confusable. What makes a model stochastic is a random draw inside its rules, and nothing else: not
whether the real process is random, not whether its results rise and fall during one run, not how
complicated it is, and not whether it is accurate.

### catch-untrustworthy

- **goal:** `w-stochastic`
- **move:** CATCH
- **answer:** Stochastic means the model has chance in its rules, so different runs give different
  results; that is what it was built to do, not a sign that it is wrong. The answer comes from
  many runs together, how often the station ran out across thousands of mornings. A deterministic
  version would give the same result every time, which makes it repeatable, not right, and since
  real riders don't come on a fixed schedule it might be further from the real morning.
- **credit:** full for naming that stochastic says the results vary from run to run because of
  chance in the rules, and says nothing about whether the model can be trusted, so a deterministic
  version is not more trustworthy for being deterministic. Half for only one side: that the
  variation is expected and many runs answer the question, or that a deterministic model is not
  more accurate, without the other. None for a different quibble alone, such as that the model
  may leave out weather or events.
- **tutor note:** a learner who says "one run isn't the answer; run thousands" has half the point;
  ask whether a deterministic version would be any closer to the truth.

### vs-deterministic

- **goal:** `w-stochastic`
- **move:** DISTINGUISH
- **answer:** A stochastic model has chance in its rules, so runs with the same settings can give
  different results, and you run many of them to see how often each result turns up. A
  deterministic model has no chance in its rules, so the same settings give the same result every
  time, and one run tells you what it will do.
- **credit:** full for naming chance in the rules as the difference, with its consequence that the
  same settings can give different results in one and always give the same result in the other.
  Half for "one is random and the other isn't" without saying what that does to the results with
  the same settings. None for an incidental difference alone, such as that stochastic models are
  more realistic, more complicated, or slower to run.

### catch-pick

- **goal:** `w-stochastic`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The model as described has no chance in its rules: the rates are
  fixed and every student takes exactly 30 seconds, so it gives the same longest line every time.
  Drawing serving times at random would put chance into its rules and make it stochastic, which is
  choice 3. Choice 1 confuses the real process with the model: rates taken from a real, random
  lunch hour are still fixed numbers once they are in the rules. Choice 2 mistakes change during
  one run for chance; the line rises and falls the same way on every run. Choice 4 mistakes a
  chain of dependent steps for chance; each wait is still fixed by the ones before it.
- **tutor note:** a learner who picks 1 is thinking of the lunch line, not the model; ask what the
  model would do if run twice with those rates.
