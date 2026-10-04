# Rubric: secret

If the learner misses a question here, set a DEFINE or INTERPRET move for secret live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A secret is a value that lets whoever holds it into something of yours: a database password, a
connection string, a token for a vendor's account. What makes it one is what holding it lets
someone do, not its name or how it looks. Its other name is credential, and that, given as an
answer, says nothing. The confusables are a setting: any value the app needs, most of which, such
as the frontend's or the backend's address, let nobody into anything and are public; and an
environment variable, which is about how a value reaches the program, not what holding it lets
someone do, so a secret may be one and a public value may be one too.

### q1

- **goal:** `w-secret`
- **move:** DISTINGUISH
- **answer:** A setting is any value the app needs, and most are harmless to show, such as the
  frontend's address. A secret is one that lets whoever holds it into something of yours, such as
  the database's connection string, so anyone who sees it could get in.
- **credit:** full for naming that a secret lets whoever holds it into something, and an ordinary
  setting doesn't. Half for saying a secret is private, sensitive or must be hidden without
  saying what makes it so. None for an incidental difference, such as that secrets have
  `PASSWORD` or `KEY` in their names, or are longer.

### q4

- **goal:** `w-secret`
- **move:** DISTINGUISH
- **answer:** An environment variable is a way of handing a value to the program, from outside its
  code; a secret is a value that lets whoever holds it into something of yours. They answer
  different questions: a secret is often handed over as an environment variable, but many
  environment variables (the frontend's address) aren't secrets, and a secret written into the
  code is still a secret.
- **credit:** full for naming that one is about how a value reaches the program and the other
  about what holding the value lets someone do, so neither implies the other. Half for an example
  that shows they come apart (a public address in an environment variable) without saying what
  each is. None for "secrets go in environment variables" or another rule about where to put
  secrets, with nothing on what separates the terms.

### q2

- **goal:** `w-secret`
- **move:** CATCH
- **answer:** Where a value is kept doesn't make it a secret; what holding it lets someone do does.
  The database password lets whoever holds it into the database, so it is a secret. The support
  email is shown to every visitor and lets nobody into anything, so it is not, even though it
  sits on the same page.
- **credit:** full for naming that being a secret depends on what holding the value lets someone
  do, not where it is kept, and so the password is one and the email is not. Half for sorting the
  two correctly without saying why, or for saying why without sorting them. None for a different
  quibble, such as that the email should be moved off the settings page.

### q3

- **goal:** `w-secret`
- **move:** CATCH
- **answer:** Being hard to guess doesn't make a value a secret. The address lets nobody into
  anything of yours; it is where anyone, including every visitor's browser, sends requests, so it
  is public.
- **credit:** full for naming that the address doesn't let whoever holds it into anything, so it
  isn't a secret however random it looks. Half for saying it is public or not a secret without
  saying why. None for a different quibble, such as that `w7mz` could in fact be guessed.
- **tutor note:** if they say "it's public because the frontend sends it to the browser", that is
  true; ask whether it would be a secret if it weren't, and what it would let someone do.
