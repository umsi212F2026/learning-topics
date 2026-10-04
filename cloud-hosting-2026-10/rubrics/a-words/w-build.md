# Rubric: build

If the learner misses a question here, set a DEFINE or INTERPRET move for build live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A build turns your code into what gets sent to the hosts: for a React frontend, `npm run build`
writes the files in `dist/`. The confusable is deploy, which puts the app where anyone's browser
can reach it. "Production build" means the same as build and is not a confusable.

### q2

- **goal:** `w-build`
- **move:** CATCH
- **answer:** The build is made from the source code, so it is not the place to fix anything. The
  next build regenerates `dist/` from the source and the typo comes back. The fix belongs in the
  source, followed by a new build.
- **credit:** full for naming that the build is generated from the source, so the next build
  overwrites the fix and the typo returns. Half for "you should fix the source" without saying why
  the fix in `dist/` won't last. None for a different quibble alone, such as that the file name is
  hard to read, that they still have to deploy, or that minified code is hard to edit.

### q3

- **goal:** `w-build`
- **move:** CATCH
- **answer:** The build is not optional. The source in `src/` (JSX, imports of packages) is not
  something a browser can load as it is; the build turns it into the plain HTML, CSS and
  JavaScript in `dist/` that the host sends. `npm run dev` only works because the dev server does
  that conversion on the laptop, which the static host won't do, so the uploaded `src/` would give
  a blank or broken page.
- **credit:** full for naming that the build is what turns the source into files a browser can
  run, so skipping it leaves the host nothing usable to send. Half for "you have to build first" or
  "upload `dist/`, not `src/`" without saying what the build does that makes it necessary. None
  for a different quibble alone, such as that the build makes the files smaller, that the app
  still needs a backend, or that they should deploy rather than upload.
- **tutor note:** a learner who says the build only makes things faster or smaller has taken the
  student's side; ask what a browser would do with a `.jsx` file.
