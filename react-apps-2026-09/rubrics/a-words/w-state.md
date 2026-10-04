# Rubric: state

### q-define-state

- **type:** free
- **goal:** w-state
- **move:** DEFINE
- **answer:** state is what the app is holding at this moment while it runs: the count so far, the
  text typed in the box, which tasks are ticked. What is on screen is worked out from it, and it
  changes as you use the app.
- **credit:** full credit for saying it is what the app is currently holding or remembering while
  it runs, with what is shown following from it. Full credit for "the data the app has right now,
  which changes as you use it". Half credit for "the app's data" with nothing about it being
  current or held while running. Do not accept "where the app saves things" or "the database",
  which is storage rather than state, and do not accept "the condition the app is in" with no
  example or no mention of what it holds.

### q-state-vs-database

- **type:** free
- **goal:** w-state
- **move:** DISTINGUISH
- **answer:** state is what the running app is holding at this moment, and it goes when the page is
  reloaded or closed unless something wrote it down. Data in a database has been written outside
  the running app, so it is still there next time, from another tab or another machine. An app
  typically loads state from the database when it starts and writes changes back.
- **credit:** full credit for the difference that matters: state lasts only as long as the page is
  running, so a reload starts it over, while saved data outlives the page and is there next time.
  Half credit for "one is temporary and one is permanent" with nothing tying the temporary one to
  the running page or the reload. Do not accept "state is in the browser and a database is on a
  server" on its own, and do not accept a difference of size or speed.

### q-list-only-in-state

- **type:** mcq
- **goal:** w-state
- **move:** INTERPRET
- **answer:** 3
- **credit:** 1 treats state as storage, which is exactly the confusion the word is against. 2 puts
  the tasks on the dev server; they are in the page, in your browser. 4 says they are already gone,
  but they are on screen and held by the app until the page is reloaded.
