# Rubric: build

### q-define-build

- **type:** free
- **goal:** w-build
- **move:** DEFINE
- **answer:** the build is the version of the project made ready to leave your laptop: `npm run
  build` takes the project's files and writes out a folder, `dist`, of files that a plain web
  server can hand to visitors, which is what you would put online. As a verb, building is running
  that command to produce it.
- **credit:** full credit for saying it is the packaged, ready-to-ship version of the project that
  npm run build produces, the thing you would put online. Full credit for the verb sense: the
  process that turns the project into that. No credit for "a production build", which names it
  again. Do not accept "running the app", "the dev server", or "checking the code for errors".

### q-build-vs-dev-server

- **type:** free
- **goal:** w-build
- **move:** DISTINGUISH
- **answer:** the dev server runs while you work: it serves the project straight from your files,
  and saved changes reach the page as you go. The build is a one-off product: the command takes the
  files as they are at that moment and writes a fixed folder of them, which does not change again
  until you build again, and which is what gets served to real visitors, with no npm or dev server
  needed where it lands.
- **credit:** full credit for the difference that matters: the dev server is live and follows your
  edits, while the build is a fixed snapshot produced on demand and meant to be served somewhere
  else. Half credit for "one is for development and one is for production" with nothing about the
  snapshot or the edits. Do not accept "the build is faster" alone, and do not accept an answer
  that treats npm run build as another way of starting the app while you work.

### q-built-once-updates

- **type:** free
- **goal:** w-build
- **move:** CATCH
- **answer:** the build is a snapshot of the files as they were when the command ran. This
  afternoon's changes are not in `dist`, and will not be until `npm run build` is run again. The
  thing that follows edits as they happen is the dev server, not the build.
- **credit:** full credit for saying dist holds what was there at build time and only another build
  puts later changes into it. Do not accept a different quibble as the error: that they should not
  have built in the morning, that dist should not be committed, or that the agent will rebuild
  without being asked.
