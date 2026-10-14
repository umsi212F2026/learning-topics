# Rubric: input validation

If the learner misses a question here, set a DEFINE or INTERPRET move for input validation live,
as help (it is recorded as helped and doesn't count), then come back to a production question.

Input validation is the server checking what arrives, before it saves or acts on it, and refusing
what isn't what it expected. The confusable is a check in the browser's form, which runs in the
visitor's browser to help honest visitors fill the form in, and which anyone who sends the server
a request without using the form skips. "Server-side validation" is another name for input
validation and is not a confusable. Lendhaven is made up, and appears nowhere else in this topic.
No host is named; nothing turns on one.

### q-catch-form-check

- **goal:** `w-input-validation`
- **move:** CATCH
- **answer:** The fourteen-day limit is a check in the browser's form, not input validation.
  Anyone who sends Lendhaven's server a loan directly, without using the form, skips it, and the
  server saves whatever return date arrives. Input validation would be the server itself
  refusing a loan longer than fourteen days, however it was sent.
- **credit:** full for naming that the check lives in the form, so a request sent without the
  form gets past it, and that input validation is a check the server makes. Half for "that's only
  the form" or "it should be checked on the server" without saying why the form's check isn't
  enough. None for a different quibble alone, such as that fourteen days is the wrong limit, or
  that the date box could be clearer.
- **tutor note:** a learner who says the form's check is still worth having is right; it helps
  honest members. Ask what happens if someone sends the server a loan without opening the form.

### q-catch-cleanup-after-saving

- **goal:** `w-input-validation`
- **move:** CATCH
- **answer:** The job checks loans after they have been saved, not when they arrive. Until it
  runs, a too-long loan is in the database and the tool shows as lent out to every other member,
  so the server has already acted on it. Input validation refuses the loan before saving it.
- **credit:** full for naming that the check comes after the loan is saved and acted on, so it
  cleans up a bad loan instead of refusing it on arrival. Half for "it should check right away"
  or "that's cleanup, not validation" without saying what happens in the meantime. None for a
  different quibble alone, such as that deleting a member's loan without telling them is rude,
  or that the job should run more often.
- **tutor note:** a learner who says the job should run every minute instead has seen that the
  delay matters; ask whether a job that runs every minute would ever refuse a loan, or only
  delete one that was already saved.

### q-input-validation-vs-form-check

- **goal:** `w-input-validation`
- **move:** DISTINGUISH
- **answer:** The form's check runs in the member's browser before anything is sent, and helps
  an honest member fill the form in, but anyone who sends Lendhaven's server a loan without the
  form skips it. Input validation runs on the server, on every loan that arrives however it was
  sent, and refuses a bad one before it is saved.
- **credit:** full for naming where each check runs and what follows from it: the form's check
  is in the browser and can be got around by not using the form, while input validation is on
  the server and applies to every request. Half for only one half, such as "the form's check can
  be skipped" with nothing on what input validation does. None for an incidental difference
  alone, such as which shows a friendlier message or which answers faster.
- **tutor note:** the question asks for the difference, not whether to keep both; a learner who
  says only "keep both" has not yet said what separates them, so ask which of the two a request
  sent without the form would meet.
