# Rubric: cache invalidation

What it names: making a cache stop handing out its old copy. Nearest confusables: reloading the
page; redeploy. Synonyms: purge, cache busting; given as an answer, either one names the thing
again and says nothing.

### q-invalidation-vs-reload

- **goal:** `w-cache-invalidation`
- **move:** DISTINGUISH
- **answer:** Reloading asks for the page again, but a cache (the browser's own, or the host's CDN)
  can answer that request with the same old copy it already has. Cache invalidation acts on the
  cache itself, making it stop handing out that old copy, so the next request gets the current
  version from the original.
- **credit:** full for the difference that matters: reloading only asks again, and a cache can
  still answer with its old copy, while invalidation makes the cache stop handing that copy out.
  Half for "reloading only changes what I see, invalidation changes it for everyone", true of a
  CDN but with nothing on the cache answering a reload. None for an incidental difference, such as
  that reloading is a button in the browser.
- **tutor note:** a learner may say a hard reload skips the browser's cache. That is right, and it
  is the browser's cache being bypassed for one request; ask what the CDN would hand that same
  request.

### q-invalidation-vs-redeploy

- **goal:** `w-cache-invalidation`
- **move:** DISTINGUISH
- **answer:** A redeploy puts a new version of the app on the host. Cache invalidation puts no new
  version anywhere; it makes a cache stop handing out its old copy so that requests reach the
  version already deployed. A redeploy that leaves the cache alone can leave visitors seeing the
  old version, and invalidating with nothing new deployed changes nothing they see.
- **credit:** full for the difference that matters: a redeploy changes what version is on the host,
  and invalidation changes only what a cache hands out, so neither one does the other's job. Half
  for describing each one correctly without saying that one can happen without the other doing
  anything. None for an incidental difference, such as that a redeploy takes longer.

### q-catch-invalidation-is-breakage

- **goal:** `w-cache-invalidation`
- **move:** CATCH
- **answer:** Cache invalidation is not the cache going wrong; it is the fix. The cache holding an
  old copy is the problem, and invalidating it is what makes it stop handing that copy out, so the
  page shows the new heading.
- **credit:** full for naming the actual error: invalidation is something done to a cache to make
  it stop handing out its old copy, not the copy going stale. Half for "invalidation fixes it"
  with nothing on what invalidation does to the cache. None for a different quibble, such as that
  the old heading might come from a deploy that failed.
