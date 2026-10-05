# Rubric: cache

What it names: a saved copy, in the browser or on the way to it, kept so it need not be fetched
again. Nearest confusable: a backup.

### q-cache-vs-backup

- **goal:** `w-cache`
- **move:** DISTINGUISH
- **answer:** A cache is a copy kept so that it can be handed out instead of fetching the original
  again; it is used in place of the original all the time, so it can be out of date, and losing it
  costs only a fresh fetch. A backup is a copy kept in case the original is lost; it isn't handed
  out in its place, only used to restore it.
- **credit:** full for the difference that matters: a cache is kept to save fetching the original
  again and is used instead of it, while a backup is kept to recover the original if it is lost.
  Half for naming one purpose correctly without the other. None for an incidental difference, such
  as that a backup is kept longer or is bigger.

### q-catch-clearing-loses-pages

- **goal:** `w-cache`
- **move:** CATCH
- **answer:** The CDN's cache holds saved copies of the pages, not the pages themselves; the
  deployed site is still on Pinecart. Clearing it throws the copies away, and the next request for
  each page is fetched again from the latest deploy, so the site stays up.
- **credit:** full for naming the actual error: the cache only holds copies, so clearing it loses
  nothing and the pages are fetched again from the deployed site. Half for "the site won't go
  down" with nothing on the cache being only a copy. None for a different quibble, such as that
  the first visitors after clearing get a slower page.

### q-catch-cache-only-in-browser

- **goal:** `w-cache`
- **move:** CATCH
- **answer:** A cache isn't only in the visitor's browser; one can sit on the way to it, such as
  a host's CDN, which keeps copies of pages and hands them to every visitor who asks. A first-time
  visitor has no copy of their own, but a CDN on the way can still hand them the old version
  until its copy is cleared or expires.
- **credit:** full for naming the actual error: caches also sit between the site and the browser,
  such as a CDN shared by every visitor, so a first-time visitor can still get an old copy. Half
  for "they might still see the old version" with nothing on a cache outside their browser. None
  for a different quibble, such as that the deploy might not have finished or might have failed.
