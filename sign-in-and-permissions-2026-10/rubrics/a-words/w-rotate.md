# Rubric: Rotate

If the learner misses a question here, set a DEFINE or INTERPRET move for rotate live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

To rotate a secret is to replace it with a new one and make the old one stop working: get a new one
from the provider, put it where the old one was (here, Rivetbox's settings), and delete or disable
the old one at the provider. The confusable is deleting the secret from the repository, which
leaves the leaked value working for anyone who already copied it, and leaves it in the history
besides.

### q2

- **goal:** `w-rotate`
- **move:** CATCH
- **answer:** Rotating includes making the old secret stop working. The old one is still valid at
  GitHub, and it is the one that leaked, so anyone who copied it can still use it; it has to be
  deleted or disabled at GitHub.
- **credit:** full for naming that the old secret still works, and rotating isn't done until it is
  deleted or disabled at the provider. Half for "delete the old one too" without saying why it
  matters that it still works. None for a different quibble alone, such as that the commit should
  also be removed from history.

### q3

- **goal:** `w-rotate`
- **move:** CATCH
- **answer:** Rotating means the new secret goes where the old one was, as well as the old one being
  deleted. Rivetbox still holds the old value, which GitHub now rejects, so sign-in on the live app
  will fail until the new secret is put in Rivetbox's settings.
- **credit:** full for naming that rotating includes putting the new secret where the old one was,
  and that the backend, still using the deleted one, will now fail to sign anyone in. Half for "put
  the new one in Rivetbox" without saying what goes wrong meanwhile, or the reverse. None for a
  different quibble alone, such as that the new secret should be stronger.

### q1

- **goal:** `w-rotate`
- **move:** DISTINGUISH
- **answer:** Deleting it from the repository only stops it being in the latest files; it is still
  in the history, and anyone who copied it can still use it, because GitHub still accepts it.
  Rotating means getting a new secret from GitHub, putting it in Rivetbox's settings where the old
  one was, and deleting the old one at GitHub, so the leaked value stops working.
- **credit:** full for naming that rotating makes the leaked secret stop working by replacing it,
  while deleting it from the repository leaves it working. Half for "rotating means getting a new
  one" without saying that the old one must stop working, or for "deleting it doesn't help" without
  saying what rotating does. None for an incidental difference alone, such as that one is done in
  git and the other on a website.
