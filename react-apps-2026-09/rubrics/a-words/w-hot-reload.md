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
  No credit for "HMR" or "hot module replacement", which are other names for it. Do not accept "the
  page reloads itself when you save" as the whole answer: the point of the word is that the running
  page is updated in place rather than being fetched and started over.

### q-hot-reload-vs-refresh

- **type:** free
- **goal:** w-hot-reload
- **move:** DISTINGUISH
- **answer:** when you refresh, the browser throws the page away, fetches the app again and starts
  it from the beginning, so whatever the app was holding goes with it. With hot reload the page
  keeps running and only the piece that changed is swapped in, and nobody asked for it: it happens
  because a file was saved.
- **credit:** full credit for both sides: a refresh starts the whole page over and loses what the
  app was holding, while hot reload updates the running page in place when a file is saved. Saying
  that something like a count may survive a hot reload and never survives a refresh is a good
  addition and is not required. Half credit for "one is automatic and one you do yourself" with
  nothing about what happens to the page. Do not accept an answer that makes hot reload a refresh
  the computer does for you.

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
  the change not having been made. Half credit for the first half alone. No credit for reading it
  as an instruction to reload the page, and no credit for concluding that the agent must not have
  saved the file, which is the one thing its message says it did.
