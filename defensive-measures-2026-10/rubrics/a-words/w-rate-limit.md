# Rubric: rate limit

If the learner misses a question here, set a DEFINE or INTERPRET move for rate limit live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

A rate limit caps how many requests one visitor may make in a stretch of time; past the cap, the
app refuses that visitor (status 429, "Too Many Requests") until the stretch is over, and goes on
answering everyone else. The confusable is an overage, which is what the host charges the app's
owner when the app as a whole uses more than the plan includes; it refuses nobody, it costs money.
"Throttling" is another name for a rate limit and is not a confusable. Ringbell and Marrowlight are
made up, and appear nowhere else in this topic.

### q-catch-limit-on-everyone

- **goal:** `w-rate-limit`
- **move:** CATCH
- **answer:** A rate limit counts each visitor's own requests, not the number of people using the
  app. Thirty-one neighbors each looking at a page or two are all served; only a single visitor
  who makes more than thirty requests in a minute is refused, and only until that minute is over.
- **credit:** full for naming that the limit is per visitor, so it counts one visitor's requests
  rather than how many neighbors use Ringbell at once. Half for "that's not how a rate limit
  works" or "it doesn't count people" without saying what it does count. None for a different
  quibble alone, such as that thirty is too low, that a minute is too short, or that pages make
  more than one request each.
- **tutor note:** a learner who says "it counts requests, not people" has half of it; ask whose
  requests: all of Ringbell's, or one visitor's.

### q-catch-refusal-is-permanent

- **goal:** `w-rate-limit`
- **move:** CATCH
- **answer:** A rate limit refuses a visitor only for a while, until the stretch of time it counts
  over has passed. Nothing has been blocked and nobody needs to unblock anything: if she stops
  refreshing and waits, Ringbell will answer her again on its own.
- **credit:** full for naming that the refusal lasts only until the stretch of time is over, so
  she is let back in without anyone doing anything. Half for "she isn't really blocked" or "it's
  not a ban" without saying that it ends by itself after a while. None for a different quibble
  alone, such as that the limit is set too low, that her account isn't involved, or that the
  builder should apologize less.
- **tutor note:** a learner who says the rate limit counts the visitor rather than the account is
  not wrong, but has not named the error; ask what she would see if she tried again in a few
  minutes.

### q-rate-limit-vs-overage

- **goal:** `w-rate-limit`
- **move:** DISTINGUISH
- **answer:** The overage is what Marrowlight charges Ringbell's builder when Ringbell as a whole
  uses more than the million requests its plan includes; it turns nobody away, it costs money. The
  rate limit is a cap Ringbell puts on each visitor; one who makes more than thirty requests in a
  minute is refused for a while, and nobody is charged.
- **credit:** full for naming who each one applies to and what it does: an overage is the host
  charging the app for using more than the plan includes, a rate limit is the app refusing a
  visitor who asks too often. Half for only one half, such as "the overage is a charge" with
  nothing on what the rate limit does. None for an incidental difference alone, such as that one
  is counted by the month and the other by the minute, or that one shows up on a bill.
- **tutor note:** a learner who says both are about "too many requests" is right that they share
  that; ask who sets each one, and who it lands on.
