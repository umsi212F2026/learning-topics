# Rubric: build

If the learner misses a question here, set a DEFINE or INTERPRET move for build live, as help (it
is recorded as helped and doesn't count), then come back to a production question.

A build turns your code into what gets sent to the hosts: for a React frontend, `npm run build`
writes the files in `dist/`. The confusable is deploy, which puts the app where anyone's browser
can reach it. "Production build" means the same as build and is not a confusable.

### q1

- **goal:** `w-build`
- **move:** DISTINGUISH
- **answer:** Only the build has happened. A build turns the code into the files that get sent to
  a host, and they are sitting in `dist/` on your laptop. Deploying puts them on a host anyone's
  browser can reach, and until that happens the classmate can't open the app.
- **credit:** full for the difference that matters (a build makes what gets sent; a deploy puts it
  where others can reach it) and for saying that only the build has happened, so the classmate
  can't open it yet. Half for the difference without saying which has happened, or for "not yet,
  it isn't deployed" without saying what the build did. None for an incidental difference alone,
  such as that the build is faster or runs on the command line.

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
