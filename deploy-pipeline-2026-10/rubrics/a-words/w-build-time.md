# Rubric: build time

What it names: the moment a value gets fixed into the frontend's files. Nearest confusable:
runtime.

### q-build-time-vs-runtime

- **goal:** `w-build-time`
- **move:** DISTINGUISH
- **answer:** A value fixed at build time is copied into the frontend's files when they are built,
  so it stays what it was then until the next build, whatever happens to the setting meanwhile. A
  value read at runtime is looked up while the app is running, so a changed value is picked up
  without building anything again.
- **credit:** full for the difference that matters: a build-time value is fixed into the files when
  they are built and needs a new build to change, while a runtime value is read as the app runs and
  a change reaches it without one. Half for "one is set when it's built, the other when it runs"
  with nothing on what changing the value takes. None for an incidental difference, such as that
  build-time values are for the frontend and runtime ones for the backend.

### q-catch-build-in-browser

- **goal:** `w-build-time`
- **move:** CATCH
- **answer:** The build happens on Pinecart before the frontend is deployed, not in the visitor's
  browser; the browser downloads files that were already built. A frontend setting's value is
  fixed into those files at build time, so changing it on the Settings page does nothing for
  visitors until the frontend is built again.
- **credit:** full for naming the actual error: the build happens on the host before deploying,
  not in the browser, so the new value reaches nobody until the next build. Half for "it needs a
  rebuild" with nothing on where or when the build happens, or the reverse. None for a different
  quibble, such as that the CDN might still serve an old copy, or that the setting might be
  misspelled.
- **tutor note:** a learner who raises the CDN has named something real that is not this
  sentence's error; ask what the new visitor would get even with the CDN's copy cleared.
