# Rubric: HTTPS

If the learner misses a question here, set a DEFINE or INTERPRET move for HTTPS live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

HTTPS is what the padlock in the address bar shows: the connection between the browser and the app
is encrypted, and the browser has checked that it is talking to the site the name says. The
confusable is HTTP, the same kind of request sent without that protection. "TLS" and "SSL" name the
protection HTTPS uses and are not confusables.

### q1

- **goal:** `w-https`
- **move:** DISTINGUISH
- **answer:** Over HTTPS, what passes between the browser and the app is encrypted, so someone else
  on the network (on café wifi, say) can't read or change it, and the browser has checked that the
  site is the one its name says; that is the padlock. Over HTTP it travels as plain text that anyone
  along the way could read or alter, and browsers mark the page "Not secure".
- **credit:** full for the difference that matters: HTTPS encrypts what travels between browser
  and app (with or without the check of the site's identity), and HTTP doesn't. Half for "HTTPS is
  secure" or "it has the padlock" without saying what it protects. None for an incidental
  difference alone, such as the extra letter, a different port, or speed.

### q2

- **goal:** `w-https`
- **move:** CATCH
- **answer:** HTTPS protects only the trip between the browser and the app. Once the data reaches
  the backend, a bug in the app, a leaked password or key, or a database left open can still expose
  it; HTTPS does nothing about any of those.
- **credit:** full for naming that HTTPS covers only the data on its way between browser and app,
  not what happens to it once it arrives. Half for "it's not completely safe" without saying what
  HTTPS does and doesn't cover. None for a different quibble alone, such as that HTTPS can be
  broken, or that the certificate might expire.
