# Rubric: routing

### q-define-routing

- **type:** free
- **goal:** w-routing
- **move:** DEFINE
- **answer:** routing is the link an app keeps between the address in the browser's bar and what is
  on screen: which screen you get is worked out from the address, and moving between screens
  changes the address to match, so an address names a particular screen and can be shared, bookmarked
  or reopened.
- **credit:** full credit for the link in either direction: the address decides which screen the
  app shows, or moving around the app updates the address to match. No credit for "client-side
  routing", which names it again. Half credit for "how you move between pages" with nothing about
  the address. Do not accept "loading a new page from the server", which is what routing in a React
  app replaces.

### q-address-changed-new-page

- **type:** free
- **goal:** w-routing
- **move:** CATCH
- **answer:** the browser did not fetch anything. With routing, the app that is already running
  changes what it shows and updates the address itself, so no new page comes from the server. That
  is why moving between screens is instant and the app keeps what it was holding.
- **credit:** full credit for saying the running app changed the screen and the address itself,
  without the browser fetching a new page from the server. Do not accept a different quibble as the
  error: that the address should have been something else, that the task page might be blank, or
  that they should reload to be sure.

### q-routing-same-page-every-address

- **type:** mcq
- **goal:** w-routing
- **move:** INTERPRET
- **answer:** 2
- **credit:** 1 describes a plain server with a file per address, which is what client-side routing
  replaces. 3 goes too far: the server does send the same page for every address, and the app then
  picks a screen from the address, which is the whole point. 4 confuses the server answering with
  the app recognising the address: the page loads either way, and an address the app knows nothing
  about shows you nothing useful.
