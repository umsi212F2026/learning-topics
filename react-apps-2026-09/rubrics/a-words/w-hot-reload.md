# Rubric: hot reload

### q-define-hot-reload

- **type:** free
- **goal:** w-hot-reload
- **move:** DEFINE
- **answer:** hot reload is the dev server noticing that a project file has been saved and pushing
  that change into the page you already have open, so what you see updates by itself, with nobody
  reloading anything.
- **credit:** full credit for saying a saved change reaches the already open page on its own, with
  nobody reloading. Mentioning the dev server pushing it in is a good addition and is not required.
  "The page reloads itself when you save" also earns full credit. Saying the running page is
  updated in place rather than fetched and started over is welcome and is not required. No credit
  for "HMR" or "hot module replacement", which are other names for it.

### q-saved-should-appear

- **type:** free
- **goal:** w-hot-reload
- **move:** INTERPRET
- **answer:** the change is already in the file, and the agent is relying on hot reload to carry it
  into the page you have open, so your tab is where it expects the result to show. If the old
  heading is still there a minute later, what is in doubt is not the change: either nothing is
  connecting your page to a running dev server, or your tab is on a different address or a
  different copy of the project from the one the agent edited.
- **credit:** full credit for both halves: the saved change should reach the open tab by itself, and
  a tab that does not change points at the dev server or at which page the tab is on rather than at
  the change not having been made. Doubting the agent's "saved" is fair, since an agent can be
  wrong about what it did: naming it beside the dev server or the tab is full credit, and naming
  only that the agent may not have saved is half. Half credit for the first half alone. No credit
  for reading it as an instruction to reload the page.
