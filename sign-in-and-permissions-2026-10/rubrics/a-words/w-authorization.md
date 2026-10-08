# Rubric: Authorization

If the learner misses a question here, set a DEFINE or INTERPRET move for authorization live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

Authorization is deciding what someone may do: whether this user may edit this recipe, see this
page, delete this account. The confusable is authentication, finding out who someone is, which in
this topic is what signing in through Google or GitHub does. Authentication comes first and
authorization uses its answer, which is why the two get run together. "Permissions" and "access
control" mean the same as authorization here and are not confusables.

### q2

- **goal:** `w-authorization`
- **move:** CATCH
- **answer:** Google only confirms who the user is, which is authentication. It knows nothing about
  the app's rule that only a recipe's author may edit or delete it; that is authorization, and the
  app itself has to decide it, by checking the signed-in user against the recipe's author on each
  edit or delete.
- **credit:** full for naming that Google's sign-in settles who the user is, not what they may do
  in this app, so the app must still decide and check who may edit or delete. Half for "Google
  doesn't do authorization" without saying what it does do or that the app must make the decision.
  None for a different quibble alone, such as that Google might be down, or that the student
  should use GitHub instead.
- **tutor note:** a learner who says the fix is to hide the Edit button from non-authors has named
  the right decision but put it where it isn't enforced; that still earns full here, since the
  word is used correctly, but it is worth a question about where the check runs.

### q1

- **goal:** `w-authorization`
- **move:** DISTINGUISH
- **answer:** Authentication is finding out who someone is, as signing in does. Authorization is
  deciding what that person may do, such as whether they may edit or delete a particular thing.
  Authentication answers "who are you?" and authorization answers "are you allowed to do this?",
  using the answer to the first.
- **credit:** full for the difference that matters: authentication establishes who someone is,
  and authorization decides what they may do. Half for one side right with the other missing or
  vague, such as "authorization is about permissions" with nothing on what authentication is.
  None for an incidental difference alone, such as which comes first, or that one uses a password,
  or the spelling.
- **tutor note:** a learner who says the two are the same thing because both happen "at sign-in"
  has run them together; ask whether two people who have both signed in may always do the same
  things.
