# Rubric: Session

If the learner misses a question here, set a DEFINE or INTERPRET move for session live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A session is the server remembering that this browser has signed in, until sign-out or expiry. The
server keeps it, and the browser carries only a cookie that points to it, so each later request is
recognized without signing in again. The confusable is signing in, the one-time act of proving who
you are, which starts a session but isn't one. A session belongs to one app's server: being signed
in at GitHub is GitHub's own session, not the app's.

### q1

- **goal:** `w-session`
- **move:** DISTINGUISH
- **answer:** Signing in is the one-time act of proving who you are, here through GitHub. The
  session is what comes after: Pantry's server remembering that this browser is signed in, so later
  requests are recognized without signing in again, until sign-out or expiry.
- **credit:** full for naming that signing in is a single event, and a session is the server
  remembering the result across later requests. Half for "the session is how long you stay signed
  in" without saying it is the server doing the remembering. None for an incidental difference
  alone, such as that signing in has a button and a session has a cookie.

### q2

- **goal:** `w-session`
- **move:** CATCH
- **answer:** A session is the server remembering that this browser has signed in; it can't live in
  React state. The server never sees React state, and a user id the frontend sends can be anything
  the user types, so the server would be taking their word for who they are.
- **credit:** full for naming that the session is kept by the server, so keeping it in React state
  leaves the server unable to tell who is signed in except by trusting the frontend. Half for "the
  server has to keep the session" without saying why the frontend's copy won't do. None for a
  different quibble alone, such as that React state is lost on refresh.
- **tutor note:** "React state is lost on refresh" is true and a reasonable second point; ask what
  would still be wrong if it weren't.

### q3

- **goal:** `w-session`
- **move:** CATCH
- **answer:** Pantry's session is Pantry's server remembering this browser, and signing out of
  Pantry ends it. Being signed in at GitHub is GitHub remembering the browser, a separate session
  that Pantry's sign-out doesn't touch and that doesn't keep Pantry's going.
- **credit:** full for naming that the session with Pantry is kept by Pantry's server and ended by
  Pantry's sign-out, and the GitHub one is separate. Half for "they're signed out of Pantry"
  without saying why GitHub doesn't matter. None for a different quibble alone, such as that they
  should also sign out of GitHub.
- **tutor note:** a learner who adds that signing in to Pantry again will be quick, since GitHub
  still remembers them, is right; that is GitHub's session at work, not Pantry's.
