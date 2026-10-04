# Rubric: CORS

If the learner misses a question here, set a DEFINE or INTERPRET move for CORS live, as help (it is
recorded as helped and doesn't count), then come back to a production question.

CORS is the browser's check on which other origins a page may call: when a page calls another
origin, the browser hands the page the response only if that origin's server says the page's
origin is allowed. The server may have answered perfectly well. Its other name is cross-origin
resource sharing, and spelling the letters out, given as an answer, says nothing. The confusable
is a server error, where the backend itself fails, such as by crashing or answering 500.

### q1

- **goal:** `w-cors`
- **move:** DISTINGUISH
- **answer:** A CORS error is the browser refusing to give the page the backend's answer, because
  the backend didn't say the page's origin is allowed; the backend may have worked fine. A server
  error is the backend itself failing to handle the request, so nothing good came back to refuse.
- **credit:** full for naming both halves: CORS is the browser blocking the response over which
  origin is allowed, while a server error is the backend failing. Half for only one half (for
  example, "a server error means the backend crashed" with nothing on what CORS is, or "CORS is
  the browser" with nothing on the server error). None for an incidental difference alone, such
  as the color of the message in the console, or which one is more common.

### q2

- **goal:** `w-cors`
- **move:** CATCH
- **answer:** CORS is a check the browser makes. curl and Postman aren't browsers and don't make
  it, so they can still call the backend whatever it allows; CORS only stops pages from other
  origins, in a browser, from reading the answers.
- **credit:** full for naming that CORS is the browser's check, so tools outside a browser are not
  stopped by it. Half for saying curl can still get through without saying why. None for a
  different quibble, such as that the setting should list more sites, or that the backend needs
  a password.
- **tutor note:** if they say "CORS is weak protection", ask who does the checking.

### q3

- **goal:** `w-cors`
- **move:** CATCH
- **answer:** The page and the file have the same origin, `https://crumbs.harbor.app`, and CORS
  only checks calls to other origins. Whatever stopped this fetch, it wasn't CORS.
- **credit:** full for naming that the call stays within the page's own origin, so CORS doesn't
  apply. Half for saying CORS isn't the cause without saying why. None for a different quibble,
  such as guessing the file is missing, with nothing on CORS.
