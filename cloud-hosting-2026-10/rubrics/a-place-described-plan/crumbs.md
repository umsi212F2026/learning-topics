Brightpage sends files only; Kettle keeps one program running; Flintlet sends files and runs short
functions but keeps no program running; Harbor offers a static site and a web service. A part is
hosted wherever it is served from, even if by another part: an Express server that sends `dist/`
itself hosts the frontend. The rule the learner should arrive at: list what each part needs (files
sent as they are; a program kept running), then check each vendor's offer against the part it was
given. Remarks about where the database goes are neither credited nor counted as a false gap; say
it belongs to the database-hosting topic. Shapes, in the entry's generator's terms: `q3` `backend-serves`, `q13` and `q14` a faulted
`backend-serves` set as two questions, `q5` `shared-vendor`, `q12` and `q15` a faulted
`shared-vendor` set as two questions, `q10` `decoy`, `q1` `split-clean`, `q6` and `q11` `one-gap`, `q2` and `q4`
`wrong-host`, `q8` a decoy across two vendors. Question ids `q7` and `q9` were about the database and are not reused.

### q1

- **goal:** `c-place-app-parts`
- **cases:** all-covered
- **answer:** Brightpage hosts the frontend's built files, Kettle the Express server; both
  covered, no gap or mismatch.
- **credit:** full for both covered, with each vendor matched to its part. Half for "both covered"
  with a vendor's job misdescribed. None if any gap or mismatch is named.

### q2

- **goal:** `c-place-app-parts`
- **cases:** mismatch
- **answer:** mismatch: Brightpage runs no code, so it cannot run the Express server. The frontend
  on Brightpage is fine.
- **credit:** full for the backend mismatch named and nothing false named; a reason (Brightpage
  runs no code) may be credited but is not required. Half for the mismatch named alongside a false
  fault against the frontend.

### q3

- **goal:** `c-place-app-parts`
- **cases:** backend-serves, all-covered
- **answer:** both covered: Kettle runs the Express server, which sends the built frontend itself,
  so no static host is needed.
- **credit:** full for both covered, saying the server sends the frontend. Half for "covered" with
  a hedge that a static host is still needed. None if the missing static host is named as a gap.
- **tutor note:** partner of `q6` and `q13`. If `q6` was served before, ask what sends the
  frontend's files here that nothing sent there.

### q4

- **goal:** `c-place-app-parts`
- **cases:** mismatch
- **answer:** mismatch: Flintlet keeps no program running between requests, so the Express server as
  written, a program that listens all the time, cannot run there without being rewritten as
  functions. The frontend on Brightpage is fine.
- **credit:** full for the backend mismatch named and nothing false named; a reason (Flintlet keeps
  nothing running) may be credited but is not required. Half for the mismatch named alongside a
  false fault against the frontend.
- **tutor note:** partner of `q8`. If `q8` was served before, ask why Flintlet was fine there.

### q5

- **goal:** `c-place-app-parts`
- **cases:** one-vendor-both, all-covered
- **answer:** both covered: one vendor, two services, Harbor's static site for the frontend and its
  web service for the Express server.
- **credit:** full for "Harbor hosts both, both covered" and nothing false named.
- **tutor note:** partner of `q12`.

### q6

- **goal:** `c-place-app-parts`
- **cases:** gap
- **answer:** gap: the frontend's code runs in the browser, but the browser has to get the files
  from somewhere, and nothing sends them: no static host, and the server doesn't send `dist/`.
  The backend on Kettle is fine.
- **credit:** full for the frontend gap named and nothing false named; a reason (its files must be
  sent from somewhere) may be credited but is not required. Half for the gap named alongside a false
  fault against the backend.
- **tutor note:** partner of `q3`. If `q3` was served before, ask how this plan differs: "last
  time the frontend had no host of its own and was fine; what is different here?"

### q8

- **goal:** `c-place-app-parts`
- **cases:** all-covered
- **answer:** both covered: Flintlet can host a folder of files, which is all the frontend needs;
  Kettle runs the Express server. Flintlet's limits matter only for a backend, and the backend isn't
  on Flintlet.
- **credit:** full for both covered. None if Flintlet is flagged as a mismatch for the frontend.
- **tutor note:** partner of `q4`. A learner who flags Flintlet here is judging the vendor rather than
  the job it was given.

### q10

- **goal:** `c-place-app-parts`
- **cases:** backend-serves, all-covered
- **answer:** both covered: Kettle runs the server, which also sends the built frontend;
  Brightpage hosting the same files again is redundant, but not a gap or a mismatch.
- **credit:** full for both covered, unless the duplicate is called a gap or a mismatch or said to
  break the app; calling it wasteful or worth tidying is fine. None if it is called a gap, a
  mismatch or something that breaks the app.

### q11

- **goal:** `c-place-app-parts`
- **cases:** gap
- **answer:** gap: a server on the learner's laptop is not reachable from visitors' browsers and is
  off whenever the laptop is, so the backend has no host. The frontend on Brightpage is fine.
- **credit:** full for the backend named as having no working host, labeled either a gap or a
  mismatch, and nothing false named; a reason (unreachable from visitors' browsers, or not always
  on) may be credited but is not required. Half for the backend's fault named alongside a false
  fault against the frontend.

### q12

- **goal:** `c-place-app-parts`
- **cases:** mismatch
- **answer:** mismatch: the Express server's code is put in a static site, which only sends files
  as they are, so the backend cannot run. The frontend in the static site is fine.
- **credit:** full for the backend mismatch named and nothing false named. Half for the mismatch
  named alongside a false fault against the frontend.
- **tutor note:** partner of `q5`. If `q5` was served before, ask: "last time Harbor hosted both and
  that was fine; what is different here?"

### q15

- **goal:** `c-place-app-parts`
- **cases:** one-vendor-both
- **answer:** the service chosen, not the vendor: Harbor offers web services, which can run the
  Express server, but the plan put the server's code in its static site, which only sends files.
- **credit:** full for the service chosen, with the reason that Harbor's web service could run the
  server. Half for "the service" with no reason. None for blaming Harbor as a vendor.

### q13

- **goal:** `c-place-app-parts`
- **cases:** mismatch
- **answer:** mismatch: Flintlet keeps no program running, so the Express server can't run there.
  (Since the server is what sends the built frontend, the frontend isn't served either; naming that
  is credited, never required.)
- **credit:** full for the backend mismatch named and nothing false named. Half for the mismatch
  named alongside a false fault.
- **tutor note:** partner of `q3`: the same arrangement on a host that can't run it.

### q14

- **goal:** `c-place-app-parts`
- **cases:** backend-serves
- **answer:** no: the server is what sends the built frontend, and the server can't run on Flintlet,
  which keeps no program running, so nothing sends the frontend's files.
- **credit:** full for "no", tied to the server being what sends the files and not running on
  Flintlet. Half for "no" with only one of those.
