# Rubric: DNS

If the learner misses a question here, set a DEFINE or INTERPRET move for DNS live, as help (it is
recorded as helped and doesn't count), then come back to a production question.

DNS is the lookup from a name to where the app is. The confusable is a domain, the name itself.
"Domain Name System" is what DNS stands for and is not a confusable.

### q1

- **goal:** `w-dns`
- **move:** DISTINGUISH
- **answer:** The domain is the name people type. DNS is the lookup that turns that name into where
  the app actually is. The agent means the name is yours but the lookup doesn't yet lead to your
  host, so typing the name won't reach the app.
- **credit:** full for the difference that matters: the domain is the name, and DNS is the lookup
  from that name to where the app is. Half for one side only. None for an incidental difference
  alone, such as that DNS is more technical, or that you pay for one and not the other.

### q2

- **goal:** `w-dns`
- **move:** CATCH
- **answer:** DNS keeps no files. It only answers where a name points, so that a browser can find
  the host; serving copies of files close to visitors is what a CDN does.
- **credit:** full for naming that DNS only looks up where a name points and holds none of the
  app's files. Naming a CDN is not required. Half for "that's not what DNS does" without saying
  what it does instead. None for a different quibble alone, such as that DNS lookups can be slow.
