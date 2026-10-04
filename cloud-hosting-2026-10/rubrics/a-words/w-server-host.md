# Rubric: server host

If the learner misses a question here, set a DEFINE or INTERPRET move for server host live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A server host keeps your backend running on its own machines, so the backend can answer each
request as it comes. The confusable is a static host, which only hands out files as they are.
"App host" and "web service" mean the same as server host and are not confusables; some vendors
use "Web Service" as their label for one.

### q2

- **goal:** `w-server-host`
- **move:** CATCH
- **answer:** The server host runs the backend itself, on its own machines, and visitors' browsers
  only get its responses. `server.js` is never sent to the browser and the browser never runs it.
- **credit:** full for naming that the backend runs on the host's machines and the browser receives
  only its responses, not the code. Half for "the browser doesn't run the backend" without saying
  where it does run. None for a different quibble alone, such as that the file might be called
  `index.js`, or that the backend needs Node installed.

### q3

- **goal:** `w-server-host`
- **move:** CATCH
- **answer:** Keeping the backend running is the server host's job. It runs `server.js` on its own
  machines and keeps it answering requests whether or not the student's laptop is on, so the
  laptop can be closed. A backend that only answers while the laptop runs it hasn't moved to a
  server host at all.
- **credit:** full for naming that the server host keeps the backend running on its own machines,
  so the app answers with the laptop off. Half for "the laptop doesn't need to be on" without
  saying what keeps the backend running instead. None for a different quibble alone, such as that
  the command might be `npm start`, that the laptop would need a public address, or that the
  frontend also has to be deployed.
- **tutor note:** if they say the laptop still matters for pushing changes, agree, and ask what
  answers a visitor's request at 3 a.m. while the laptop is closed.
