Harbor hosts two parts, each at its own address, so "your Harbor address" does not settle which
part a setting needs: the learner has to work it out from what the setting is for. What each
setting is for is in the agent's answer; accept any wording that says the same thing. A value is
a secret when someone holding it could get into something of yours; an address the app's users
see is not.

### q1

- **goal:** `c-trace-setting-value`, `c-spot-secret`
- **answer:** It is where the React app sends its requests. It needs the backend's address: the
  web service's, `https://crumbs-k3x9.harbor.app`, not the static site's. Not a secret: anyone
  using the app can see where its requests go.
- **credit:**
  - `c-trace-setting-value`: full for the purpose and the backend's (web service's) address; half
    for the purpose with the wrong Harbor address, or for "Harbor's address" without saying which.
  - `c-spot-secret`: full for "not a secret" with a reason like the address being public; half for
    "not a secret" with no reason.
- **tutor note:** the near-miss is copying the first Harbor address in sight, often the static
  site's. Ask where the requests go.
