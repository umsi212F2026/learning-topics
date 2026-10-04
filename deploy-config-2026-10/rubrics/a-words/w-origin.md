# Rubric: origin

If the learner misses a question here, set a DEFINE or INTERPRET move for origin live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

An origin is where a page was loaded from, down to the port: `http://localhost:5173`, or
`https://crumbs.harbor.app`. It stops at the port, so a page's path is not part of it, and two
addresses with the same domain but different ports, such as `http://localhost:5173` and
`http://localhost:3000`, are different origins. The confusable is domain, the machine's name alone
(`localhost`, `crumbs.harbor.app`).

### q1

- **goal:** `w-origin`
- **move:** DISTINGUISH
- **answer:** The domain is only the machine's name, such as `localhost`. The origin is where the
  page was loaded from, down to the port (with the `http` or `https` in front), so
  `http://localhost:5173` and `http://localhost:3000` share a domain but are two different
  origins.
- **credit:** full for naming that the origin goes down to the port (and the scheme) while the
  domain is only the name, so the same domain can be more than one origin. Half for saying the
  origin is "more of the address" or "the full address" without saying the port is what makes the
  difference. None for an incidental difference, such as that a domain is bought, or that one has
  `www` in it.

### q4

- **goal:** `w-origin`
- **move:** DISTINGUISH
- **answer:** A full URL names one particular page or file: the drill's page. An origin names the place
  pages are loaded from, down to the port, and every page on that site shares it, so it is what
  a browser or a backend compares when it asks where a page came from.
- **credit:** full for naming that a full URL picks out one page or resource, while an origin
  names the place it was loaded from, shared by every page there. Half for saying only that the
  origin is the URL without the path, with nothing on what each one names. None for an
  incidental difference alone, such as length, or that one has a slash.
- **tutor note:** this one asks what each names, not only that the path is dropped. If the answer
  only says "drop the path", ask what two different tool pages on Lendlist have in common.

### q2

- **goal:** `w-origin`
- **move:** CATCH
- **answer:** An origin stops at the port; it doesn't include the path. Every page on that site has
  the same origin, `https://crumbs.harbor.app`, whichever recipe is open.
- **credit:** full for naming that the path (`/recipes/42`) is not part of the origin, which is
  `https://crumbs.harbor.app`. Half for giving the right origin without saying why the path is
  dropped, or for saying the origin is "too long" without saying what to cut. None for a
  different quibble, such as that the recipe number is private.

### q3

- **goal:** `w-origin`
- **move:** CATCH
- **answer:** An origin is where a page was loaded from, not where its requests go. The requests
  come from pages loaded from the frontend, so the origin the backend should accept is the
  frontend's, `https://crumbs.harbor.app`.
- **credit:** full for naming that the origin is where the calling page came from, so the setting
  needs the frontend's address. Half for giving the frontend's address without saying why, or for
  saying origin means where the page came from without saying which address that is here. None
  for a different quibble, such as the setting's name, or that both addresses are on Harbor.
- **tutor note:** if they answer with the frontend's address but no reason, ask what an origin
  describes: the page, or the place it sends to.
