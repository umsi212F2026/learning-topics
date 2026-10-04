# Rubric: server host

If the learner misses a question here, set a DEFINE or INTERPRET move for server host live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A server host keeps your backend running on its own machines, so the backend can answer each
request as it comes. The confusable is a static host, which only hands out files as they are.
"App host" and "web service" mean the same as server host and are not confusables; q1 uses "Web
Service" as a vendor's label for one, as some vendors do.

### q1

- **goal:** `w-server-host`
- **move:** DISTINGUISH
- **answer:** The Web Service. It is a server host: it keeps the Express program running so it can
  answer each request. A Static Site only hands out files as they are and runs nothing of yours, so
  the backend would never run there.
- **credit:** full for choosing the Web Service and naming the difference that matters: a server
  host keeps your program running to answer requests, a static host only hands out files. Half for
  the right choice with no difference named, or with only "one is for backends". None for an
  incidental difference alone, such as price or which one has more settings.

### q2

- **goal:** `w-server-host`
- **move:** CATCH
- **answer:** The server host runs the backend itself, on its own machines, and visitors' browsers
  only get its responses. `server.js` is never sent to the browser and the browser never runs it.
- **credit:** full for naming that the backend runs on the host's machines and the browser receives
  only its responses, not the code. Half for "the browser doesn't run the backend" without saying
  where it does run. None for a different quibble alone, such as that the file might be called
  `index.js`, or that the backend needs Node installed.
