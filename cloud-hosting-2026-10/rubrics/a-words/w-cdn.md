# Rubric: CDN

If the learner misses a question here, set a DEFINE or INTERPRET move for CDN live, as help (it is
recorded as helped and doesn't count), then come back to a production question.

A CDN keeps copies of your files close to wherever the visitor is, in many places at once, so each
visitor gets them from somewhere nearby. The confusable is a static host, the host that hands out
your frontend's files as they are. Many static hosts serve through a CDN of their own, which is why
the two are confused. "Content delivery network" and "edge network" mean the same as CDN and are
not confusables.

### q1

- **goal:** `w-cdn`
- **move:** DISTINGUISH
- **answer:** A static host is where your frontend's files are put to be handed out as they are. A
  CDN is about where copies of files are kept: in many places, close to visitors, so each one gets
  them from nearby. A static host may serve through a CDN or may not, and a CDN can sit in front of
  other kinds of host too.
- **credit:** full for the difference that matters: a CDN is copies kept in many places near
  visitors, while a static host is the host that serves your files, which may or may not use one.
  Half for the CDN side alone (copies near visitors) with nothing on how a static host differs.
  None for an incidental difference alone, such as "a CDN is faster" with no reason, or price.
- **tutor note:** a learner who says "they're the same thing" because their host has a CDN has met
  the overlap; ask whether a static host with a single machine in one city would still be a static
  host.

### q2

- **goal:** `w-cdn`
- **move:** CATCH
- **answer:** A CDN keeps copies of files, not a running backend. The frontend's files come from
  nearby, but every request to the Express backend still travels to the one server host where it
  runs.
- **credit:** full for naming that a CDN holds copies of files and doesn't run the backend, so
  backend requests still go to the one region. Half for "the backend isn't on the CDN" without
  saying what the CDN does hold. None for a different quibble alone, such as that the server host
  should be in a different region.
