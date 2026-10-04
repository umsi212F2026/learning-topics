# Rubrics: The words of react apps

Answers for `tasks/items.md`. **Do not read this before attempting the questions.**

### q-links-expire-request

- **type:** free
- **goal:** c-describe-app-bug
- **answer:** any two of these three. It gives no address, so the agent doesn't know which link
  was opened and can't make the problem happen for itself. It never says what the page should have
  shown instead (the task's text), so the agent has no way to tell when it's fixed. And the second
  sentence, that the links expire, is a guess about the cause written as though it had been seen.
  Nobody can see a link expire; what was seen is a blank page. An agent that takes it as fact may
  go looking for an expiry to remove and leave the real cause alone.
- **credit:** full credit for any two of the three, half credit for one. Missing steps, such as
  how the link was opened or how to get to the page, count as the missing address, not as a
  separate problem, so naming both the address and the steps is still only one. No credit for
  calling "blank" unclear, for answers about tone, length or politeness, or for treating the first
  sentence as the guess. A missing detail about the expiry itself, such as how long links last,
  earns nothing, since it takes the guess as fact.

### q-fixed-when-line

- **type:** free
- **goal:** c-describe-app-bug
- **answer:** it says what the app should do when the problem is gone, in a form anyone can check,
  so whoever fixes it knows when they are finished and you can tell whether the fix worked. The
  rest of the request says what went wrong and how to make it happen again; without this line,
  "fixed" is left to the agent's judgment, and it may stop at something that only changes the
  symptom.
- **credit:** full credit for naming it as the checkable test for when the work is done, letting
  you or the agent tell whether the fix worked. Half credit for "it says what should happen
  instead" with nothing about telling whether it is fixed. No credit for "it summarises the
  request", "it is polite", or treating it as the labeled guess.

### q-first-line-of-error

- **type:** free
- **goal:** c-run-browser-check
- **answer:** the lines you left out are the ones that say where the error came from, and they are
  often the only part of the report that points at what to look at. The agent has the message but
  not the where, so it either asks you for the rest or guesses. A check is reported complete and
  unedited, pasted as it appeared, warnings included, rather than summarised.
- **credit:** full credit for saying the omitted lines carry what the agent needs, where the error
  happened, so it has to ask again. Half credit for "it wasn't complete" with no account of what
  was lost. No credit for saying a screenshot would have been better (the text could be copied), or
  for blaming the error itself rather than the report.

### q-which-tab-snippet

- **type:** mcq
- **goal:** c-run-browser-check
- **answer:** 4
- **credit:** the console belongs to one tab, so 1 is false and its number would come from the
  documentation page. 2 and 3 both report something that is not your app, which is the thing the
  request was about; where the request does not name a tab, the app is the tab it meant. Declining
  to run a snippet anywhere other than your own app is the same habit at work.
