# Rubric: Client secret

If the learner misses a question here, set a DEFINE or INTERPRET move for client secret live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A client secret is the private value that proves to the provider a request comes from your app's
server. There is one for the app, issued when you register it, and it stays on the backend host,
never in the frontend or the repository. The confusables are the client ID, which names your app
to the provider and is public, so it may sit in the frontend; and a user's password, which belongs
to one user, proves who that person is to the provider, and is never seen by your app.

### q1

- **goal:** `w-client-secret`
- **move:** DISTINGUISH
- **answer:** The client ID names your app to GitHub and is public; it can go in the frontend and
  shows up in the address the browser is sent to. The client secret proves that a request comes
  from your app's server, so it must stay private, on the backend host only.
- **credit:** full for naming that the ID only identifies the app and is public, while the secret
  proves a request is really from your server and must be kept private. Half for "one is public,
  one is private" without saying what the secret is for. None for an incidental difference alone,
  such as that the secret is longer or that they are shown on different lines of the settings
  page.

### q2

- **goal:** `w-client-secret`
- **move:** DISTINGUISH
- **answer:** The client secret belongs to your app: there is one for the whole app, and it proves
  to GitHub that a request comes from your server. A user's password belongs to that user and
  proves who they are to GitHub; your app never sees it.
- **credit:** full for naming that the client secret proves your app's server to the provider,
  while a password proves a user's identity, and the app never handles the user's password. Half
  for "one is the app's, one is the user's" without saying what each proves. None for an
  incidental difference alone, such as that a password is chosen by a person and a secret is
  generated.

### q3

- **goal:** `w-client-secret`
- **move:** CATCH
- **answer:** There is one client secret for the whole app, issued when the app is registered with
  GitHub, not one per user. It proves requests come from the app's server, so it lives in the
  backend host's settings, not in a table of users.
- **credit:** full for naming that the client secret belongs to the app, one for all users, and
  proves the app's server rather than anything about a user. Half for "there's only one client
  secret" without saying whose it is or what it proves. None for a different quibble alone, such
  as that the column should be encrypted.
- **tutor note:** a learner who says "they mean the token" may be right about what the student
  meant to store; ask what the client secret is, then, and where it does belong.
