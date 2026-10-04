# Rubric: hard reload

### q-define-hard-reload

- **type:** free
- **goal:** w-hard-reload
- **move:** DEFINE
- **answer:** a hard reload is a reload in which the browser is told not to use the copies of the
  app's files it kept from last time, and to fetch them again. It is what you do when the page may
  be showing you an old version of the app rather than the one being served now.
- **credit:** full credit for saying it reloads without using what the browser kept from before,
  fetching the files again instead of reusing saved copies. No credit for "a hard refresh" or "a
  force reload", which name it again. Half credit for "a stronger reload" or "it clears the cache"
  with nothing about the page's files being fetched again. Do not accept "it restarts the app",
  which an ordinary reload does too.

### q-hard-reload-vs-reload

- **type:** free
- **goal:** w-hard-reload
- **move:** DISTINGUISH
- **answer:** both throw the page away and start it again. An ordinary reload may reuse files the
  browser saved from last time, so an old version of the app can come straight back up. A hard
  reload tells the browser not to trust those and to fetch the app's files again, so what you get
  is what is being served now.
- **credit:** full credit for the difference that matters: an ordinary reload may reuse the
  browser's saved copies, and a hard reload fetches the files again. Half credit for "a hard reload
  is more thorough" with nothing about the saved copies. Do not accept a difference of degree, the
  keyboard shortcut alone, or an answer in which a hard reload clears your data or logs you out.

### q-hard-reload-looked-same

- **type:** free
- **goal:** w-hard-reload
- **move:** CATCH
- **answer:** looking the same is what you would expect here. The difference is in where the page's
  files came from, not in what appears on screen: when nothing the browser kept was out of date,
  an ordinary reload and a hard reload give you the same page. The difference shows only when the
  browser is holding an old copy of the app.
- **credit:** full credit for saying the two look the same whenever the browser had nothing stale,
  because what differs is where the files come from rather than what is shown. Do not accept a
  different quibble as the error: that they pressed the wrong keys, that they should clear the
  cache from the browser's settings instead, or that the starter app is too small to have anything
  saved.
