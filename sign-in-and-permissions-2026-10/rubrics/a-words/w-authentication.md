# Rubric: Authentication

If the learner misses a question here, set a DEFINE or INTERPRET move for authentication live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

Authentication is finding out who someone is. In this topic it is what signing in through Google or
GitHub does: the provider vouches for the user, and the app learns who they are without ever
holding a password. It is not deciding what that person may do, which is authorization, and it does
not require the app itself to check a password. The word has no confusable or synonym listed, so
both questions are CATCH.

### q1

- **goal:** `w-authentication`
- **move:** CATCH
- **answer:** The check doesn't find out who the user is; that was settled when they signed in
  through GitHub. It decides whether this already-known user may delete this recipe, which is
  authorization, not authentication.
- **credit:** full for naming that authentication is finding out who someone is, and this check
  instead decides what a known user may do. Half for "that's authorization" with nothing on what
  authentication is or why the check isn't it. None for a different quibble alone, such as that
  the check should also allow admins, or that it belongs in a middleware.

### q2

- **goal:** `w-authentication`
- **move:** CATCH
- **answer:** Pantry does know who each member is, without a password of its own: signing in
  through GitHub is authentication, since GitHub vouches for who the user is and Pantry keeps their
  GitHub id, so it can record that id on each recipe they post. Checking a password yourself is
  only one way to authenticate.
- **credit:** full for naming that authentication means establishing who the user is, which
  sign-in through GitHub does for Pantry without a password of Pantry's own, so Pantry does know
  who posted each recipe. Half for "GitHub sign-in tells Pantry who they are" without connecting
  it to authentication not needing Pantry's own password, or for "that's authentication through
  GitHub" without saying Pantry then knows the member. None for a different quibble alone, such as
  that Pantry should store passwords as a fallback.
- **tutor note:** a learner who agrees, thinking an app knows who someone is only by checking a
  password, has the error this question targets; ask what Pantry gets back from GitHub after a
  member signs in.
