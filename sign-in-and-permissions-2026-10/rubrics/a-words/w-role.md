# Rubric: Role

If the learner misses a question here, set a DEFINE or INTERPRET move for role live, as help (it is
recorded as helped and doesn't count), then come back to a production question.

A role is a named level of what a group of users may do in your app, such as member or admin. Many
accounts share a role, the app itself assigns it and stores it, and the server checks it. The
confusable is an account, which is one user's own identity in the app, here keyed by their GitHub
id; an account has a role, but is not one. "Permission level" is another name for a role, not a
confusable.

### q1

- **goal:** `w-role`
- **move:** DISTINGUISH
- **answer:** An account is one person's identity in Pantry, such as Priya's, tied to her GitHub id.
  A role is a level of what a group of users may do, such as member or organizer; many accounts
  share one role, and each account has a role.
- **credit:** full for naming that an account is one user and a role is a level of what a group of
  users may do, shared across accounts. Half for one side right with the other vague, such as "a
  role is admin or member" with nothing on what an account is. None for an incidental difference
  alone, such as that accounts have pictures and roles don't.

### q2

- **goal:** `w-role`
- **move:** CATCH
- **answer:** A role is a level shared by a group of users, not one per person. These three need the
  same thing, so they want one role, such as organizer, allowed to delete any recipe, given to each
  of their accounts.
- **credit:** full for naming that a role is a level for a group, so one organizer role given to all
  three is what's wanted, not one per person. Half for "use one admin role" without saying why a
  role per person misses the point. None for a different quibble alone, such as the role names'
  spelling.
- **tutor note:** if they ask what's wrong with it if it works, ask what happens when a fourth
  person starts helping run the club.

### q3

- **goal:** `w-role`
- **move:** CATCH
- **answer:** A role is a level in Pantry itself, so Pantry decides it and stores it, for instance in
  its `users` table. GitHub only tells Pantry who the user is; it knows nothing of who runs the
  cooking club.
- **credit:** full for naming that a role belongs to the app, which has to assign and store it,
  since the provider only says who the user is. Half for "Pantry has to store it" without saying why
  GitHub can't supply it. None for a different quibble alone, such as that roles should be
  hard-coded.
