# Rubric: root cause

### q-define-root-cause

- **type:** free
- **goal:** w-root-cause
- **move:** DEFINE
- **answer:** the thing actually responsible for the problem, the one that explains it, as against
  what you first noticed. Fix it and the problem stops for a reason someone can state; what you
  noticed is usually several steps downstream of it.
- **credit:** full credit for "the underlying reason the problem happens", set against what was
  noticed or what the problem looks like from outside. Half credit for "the reason for the bug"
  with nothing separating it from the symptom. No credit for "the bug", "the error message", or
  "the part of the app where the problem shows up", which are the symptom or where it surfaced.

### q-root-cause-vs-symptom

- **type:** free
- **goal:** w-root-cause
- **move:** DISTINGUISH
- **answer:** the symptom is what can be seen from outside: the note does not appear in the list
  after you save it. The root cause is whatever makes that happen, and it could be any of several
  things: the save never reaching the server, the server not storing it, the list being read from
  somewhere the note was never written. The symptom looks the same whichever it is, which is why it
  does not tell you what to fix.
- **credit:** full credit for placing the two: the symptom is the behavior observed, the root cause
  is the underlying reason that produced it, and one symptom can have several possible causes. Half
  credit for "the symptom is the effect and the cause is the cause" with nothing tied to this
  situation. No credit for treating them as the same thing, and no credit for naming one guessed
  cause as though the guess were the definition.

### q-catch-root-cause-workaround

- **type:** free
- **goal:** w-root-cause
- **move:** CATCH
- **answer:** nobody found out why the note was missing from the list. The reload covers the
  symptom up while the cause is still there, so it will show up again anywhere else that path is
  used, and the app now does an extra reload for a reason nobody can state.
- **credit:** full credit for saying the symptom was hidden and the underlying reason was never
  found, so the cause is still there. Naming a consequence, that it will come back elsewhere or
  that nobody can say why the fix works, is a good addition and is not required. Do not accept a
  different quibble as the error: that reloading is slow or ugly, that the agent should have
  written a test, or that they should have asked the agent for more detail.
