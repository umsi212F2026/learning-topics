# Rubric: cache invalidation

What it names: making a cache stop handing out its old copy. Nearest confusables: reloading the
page; redeploy; cache busting. Synonym: purge; given as an answer, it names the thing again and
says nothing.

### q-invalidation-vs-reload

- **goal:** `w-cache-invalidation`
- **move:** DISTINGUISH
- **answer:** Reloading the page is one person asking for the page again; at most it makes their
  own browser skip its saved copy, and any cache on the way, such as a CDN's, can still hand back
  the old one. Cache invalidation is done to the cache itself: it drops its old copy, so the next
  request from anyone gets a fresh one.
- **credit:** full for the difference that matters: reloading is one person asking again, which
  changes nothing in the cache, while invalidation makes the cache itself drop its old copy, for
  every visitor. Half for "a reload only affects you" with nothing on invalidation acting on the
  cache. None for an incidental difference, such as that a reload is a button in the browser and
  invalidation is done on the host.
- **tutor note:** a learner may say a hard reload skips the cache. Ask which cache: it skips the
  browser's own copy, and a CDN on the way may still hand back its old one.

### q-invalidation-vs-redeploy

- **goal:** `w-cache-invalidation`
- **move:** DISTINGUISH
- **answer:** A redeploy puts a new version of the app on the host. It does nothing to a cache's
  copies by itself, so a cache can go on handing out the old version afterwards. Invalidation
  changes nothing on the host; it makes the cache drop its old copy so that the next request
  fetches whatever is deployed now.
- **credit:** full for the difference that matters: a redeploy changes what is on the host, and
  invalidation changes what the cache hands out, so a redeploy alone can leave the old copy being
  served. Half for "a redeploy puts the new version up and invalidation clears the cache" with
  nothing on a redeploy leaving the cache's old copy in place. None for an incidental difference,
  such as that a redeploy takes longer.
- **tutor note:** a learner may say a redeploy clears the cache. Some hosts do both at once, as
  Pinecart does with "Clear CDN cache on deploy" on; ask what a visitor would get if that setting
  were off.

### q-invalidation-vs-busting

- **goal:** `w-cache-invalidation`
- **move:** DISTINGUISH
- **answer:** Invalidation makes the cache drop its old copy, so everyone who asks for that address
  afterwards gets the new version. Cache busting leaves the cache alone and asks for a different
  address, such as the page with `?v=2` added, which the cache has no copy of. Only requests for
  the new address get past the cache; anyone still asking for the old address gets the old copy.
- **credit:** full for the difference that matters: invalidation makes the cache drop its copy for
  everyone, while busting sidesteps the cache by asking for a different address, which helps only
  whoever asks for that address. Half for "busting changes the address and invalidation clears the
  cache" with nothing on who then gets the new version. None for an incidental difference, such as
  that busting is done by the developer and invalidation by the host, or that busting is quicker.
- **tutor note:** a learner may say a site that always links to the new address reaches everyone.
  That is true when the address is changed in the site's own links; ask who gets past the cache
  when one person types `?v=2` into their own address bar.

### q-catch-invalidation-reaches-browsers

- **goal:** `w-cache-invalidation`
- **move:** CATCH
- **answer:** Pressing Clear CDN cache invalidates the CDN's cache, so the CDN stops handing out
  its old copy and fetches the new version on the next request. It does nothing to the copies in
  visitors' browsers, which are separate caches; a visitor gets the new version only when their
  browser asks again, for example when they reload.
- **credit:** full for naming the actual error: the invalidation reached only the CDN's cache, and
  each visitor's browser keeps its own copy until it asks again. Half for "they still have to
  reload" with nothing on the browser keeping a separate copy. None for a different quibble, such
  as that the CDN might take a little while to clear, or that the new version might have a bug.
