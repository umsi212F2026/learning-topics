# Rubric: Silent failure

If the learner misses a question here, set a DEFINE or INTERPRET move for silent failure live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A silent failure is something going wrong with nothing to say so, so the run looks as if it worked.
The reading gives two ways it happens: the step could tell something went wrong but says so only
somewhere nobody will look, such as a log nobody reads, or not at all, such as by skipping the item;
or the result is wrong but looks right, and nothing checks it. A failure that stops the run with an
error a person sees is not silent, however annoying. Being found later by chance doesn't make a
failure loud after the fact: what makes it silent is that nothing reported it. The word has no
nearest confusable in goals.md, so this bank has no DISTINGUISH question.

### catch-pick

- **goal:** `w-silent-failure`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The step skipped a recipe and reported it nowhere, and the run looked
  as if it had worked: a silent failure. Choice 1 takes Ana's chance discovery as a report; nothing
  told her, so the failure was still silent. Choice 2 stretches the word to any failure: an error
  on her screen is exactly something saying so. Choice 4 misses that a report where Ana will see
  it is what ends the silence.

### catch-plant-log

- **goal:** `w-silent-failure`
- **move:** CATCH
- **answer:** Writing an error to a log doesn't stop it being a silent failure if nobody reads the
  log, and Malik never opens it, so a sensor that doesn't answer still goes unnoticed. And some
  failures never reach the log at all: if the agent misreads a reading and says a dry plant is
  fine, that isn't an error the step hits, and the list looks right.
- **credit:** full for either reason, explained: that an error written only to a log nobody reads is
  still a silent failure, since nothing reaches a person; or that a wrong result that looks right,
  such as the agent misjudging a plant, is never logged as an error, so it goes unreported. Both is
  welcome, not required. Half for "he never reads the log" or "the agent could get it wrong" with
  nothing tying it to why the failure would go unnoticed. None for a different quibble alone, such
  as that the sensors should be more reliable.
- **tutor note:** a learner who gives only the log reason has passed; if time allows, ask what
  would happen if the agent called a dry plant fine, to bring out the second way.
