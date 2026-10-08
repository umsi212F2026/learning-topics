# Rubric: Scope

If the learner misses a question here, set a DEFINE or INTERPRET move for scope live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A scope is what your app asks the provider to let it see or do with the user's account at the
provider: their name and picture, their email, their repositories. It limits the app, at the
provider. The confusable is a role, a named level in your own app of what a group of users may do
there, such as member or admin; it limits users, in your app, and the provider knows nothing of
it.

### q2

- **goal:** `w-scope`
- **move:** CATCH
- **answer:** A scope only covers what Pantry may see or do with the user's GitHub account. Deleting
  recipes happens in Pantry, not at GitHub, so no scope grants it; Pantry gives organizers a role,
  such as admin, and its server checks that role.
- **credit:** full for naming that a scope is about the user's account at GitHub, so it can't grant
  anything inside Pantry, which needs its own role or rule. Half for "use a role instead" without
  saying why a scope can't do it. None for a different quibble alone, such as that organizers
  should not delete other people's recipes.

### q3

- **goal:** `w-scope`
- **move:** CATCH
- **answer:** A scope is what the app is allowed to see or do with the user's account, not just
  wording. Granting `repo` lets Pantry, and anyone who gets hold of what Pantry holds, reach every
  member's repositories, which Pantry has no use for; it should ask only for what it needs to read
  a name and picture.
- **credit:** full for naming that a scope sets what the app can actually see or do with the user's
  account, so `repo` gives Pantry access to repositories it doesn't need. Half for "ask for less"
  or "users won't approve it" without saying that the scope changes what the app can do. None for
  a different quibble alone, such as the exact name of a smaller scope.

### q1

- **goal:** `w-scope`
- **move:** DISTINGUISH
- **answer:** A scope is what the app asks GitHub to let it see or do with the user's GitHub
  account, such as reading their name. A role is a level inside the app itself, such as member or
  admin, saying what a group of users may do in the app. A scope limits the app at GitHub; a role
  limits users in the app.
- **credit:** full for naming that a scope is about what the app may see or do with the user's
  account at the provider, and a role is about what users may do in the app. Half for one side
  right with the other vague, such as "a role is member or admin" with nothing on what a scope
  covers. None for an incidental difference alone, such as that scopes are set in code and roles in
  the database.
