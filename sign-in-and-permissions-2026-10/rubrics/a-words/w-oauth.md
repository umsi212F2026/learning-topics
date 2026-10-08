# Rubric: OAuth

If the learner misses a question here, set a DEFINE or INTERPRET move for OAuth live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

OAuth is the standard way an app lets you sign in with an account you already have elsewhere,
such as Google or GitHub. You prove who you are to that provider, on its own page; the app gets
back who you are, and only what you agreed to share, and never sees your password. The
confusables are basic auth, where the app itself takes and checks a username and password it
holds, and simply giving the app your Google password, which hands it your whole account.

### q1

- **goal:** `w-oauth`
- **move:** DISTINGUISH
- **answer:** With basic auth your app holds the passwords and checks the one the browser sends.
  With OAuth the user signs in to an account they already have, at GitHub, and GitHub tells your
  app who they are; your app never sees or keeps a password.
- **credit:** full for naming that under basic auth the app itself takes and checks a password,
  while under OAuth an outside provider checks who the user is and the app never handles the
  password. Half for one side right with the other vague, such as "OAuth uses GitHub" with nothing
  on what changes about the password. None for an incidental difference alone, such as that
  OAuth is newer, has a nicer screen, or that basic auth sends the password with every request.

### q2

- **goal:** `w-oauth`
- **move:** DISTINGUISH
- **answer:** With OAuth you type your password only on Google's own page; the app never sees it,
  and gets back only who you are and what you agreed to share. Typing your Google password into
  the app's form hands the app the password itself, and with it your whole Google account, which
  it could keep or misuse.
- **credit:** full for naming that under OAuth the app never receives your Google password and gets
  only what you approved, while the form gives the app the password and so your whole account.
  Half for "the form is a phishing risk" or "the second one is unsafe" without saying what the app
  gets in each case. None for an incidental difference alone, such as which looks more
  professional or which takes fewer clicks.

### q3

- **goal:** `w-oauth`
- **move:** CATCH
- **answer:** With OAuth the app doesn't hold users' passwords at all. Users sign in at the
  provider, which tells the app who they are, and the app keeps the provider's id for each user,
  not a password, hashed or otherwise.
- **credit:** full for naming that under OAuth there is no password for the app to store, because
  the provider checks it, and the app keeps the provider's id instead. Half for "OAuth doesn't use
  passwords" without saying who checks the password or what the app keeps. None for a different
  quibble alone, such as which hashing method to use.
- **tutor note:** a learner who says "the app stores a token instead" is close; ask what the app
  needs to remember about a user to recognize them next time.
