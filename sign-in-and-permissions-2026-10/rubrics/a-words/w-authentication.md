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
- **answer:** Authentication is finding out who someone is, and Pantry does that: it signs users in
  through GitHub, which vouches for who they are, and Pantry keeps their GitHub id. Checking a
  password yourself is only one way to authenticate; handing that part to GitHub is still
  authentication.
- **credit:** full for naming that authentication means establishing who the user is, which
  sign-in through GitHub does for Pantry, so it doesn't need a password of Pantry's own. Half for
  "signing in with GitHub is authentication" without saying why a password isn't needed for it.
  None for a different quibble alone, such as that Pantry should store passwords as a fallback.
- **tutor note:** a learner who says "GitHub does the authentication, not Pantry" has the idea
  nearly right; ask whether Pantry ends up knowing who the user is, and how.
