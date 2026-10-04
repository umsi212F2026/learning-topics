# Rubric: static host

If the learner misses a question here, set a DEFINE or INTERPRET move for static host live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

A static host hands out the frontend's files as they are and runs none of your code. The
confusable is a server host, which keeps your backend running so it can answer each request.
"Static site hosting" means the same as static host and is not a confusable.

### q1

- **goal:** `w-static-host`
- **move:** DISTINGUISH
- **answer:** A static host only hands out files as they are; nothing of yours runs on it. A server
  host keeps your program running so it can work out an answer to each request. The built React
  files in `dist/` need only to be handed out, so a static host will do; the Express backend has to
  be running, so it needs a server host.
- **credit:** full for the difference that matters (a static host hands out files and runs nothing
  of yours; a server host keeps a program running) and for placing the frontend on the static host
  and the backend on the server host. Half for the right placement with only "one is for the
  frontend and one for the backend" as the difference, or for the difference with no placement.
  None for an incidental difference alone, such as price, speed, or that static hosts are for small
  sites.

### q2

- **goal:** `w-static-host`
- **move:** CATCH
- **answer:** The static host doesn't run the React code either. It hands out the built files as
  they are, and the React code runs in each visitor's browser. Uploading `server.js` would only make
  it one more file to download; nothing would run it.
- **credit:** full for naming that the static host runs none of the code, the React code runs in the
  browser, so it cannot run Express. Half for "a static host can't run a server" without
  correcting the claim that it runs the React code. None for a different quibble alone, such as
  that Express needs a database, or that `server.js` should be in another folder.
- **tutor note:** if the learner says only "it can't run Express", ask where the React code runs
  when someone opens the page.
