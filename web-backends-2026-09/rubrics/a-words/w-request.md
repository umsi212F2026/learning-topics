# Rubric: request

### q-request-vs-page-load

- **type:** free
- **goal:** w-request
- **move:** DISTINGUISH
- **answer:** loading the page is the browser fetching the page's own files and starting the app
  over from nothing, so whatever the running app was holding is gone. A request is one trip the
  already-running page makes out to the server and back, asking for something or sending something.
  The page carries on running, and usually only the part of the screen that the answer bears on
  changes.
- **credit:** full credit for the difference that matters: a load starts the page over from its
  files, while a request is one ask-and-answer made by a page that is already running and keeps
  running. Half credit for "a load is the whole page and a request is only part of it", with nothing
  about the page continuing to run. Do not accept a difference of speed or size on its own, and do
  not accept an answer in which every request reloads the page.

### q-request-sort-is-request

- **type:** free
- **goal:** w-request
- **move:** CATCH
- **answer:** something changing on screen does not mean anything left the page. A request is a trip
  out to the server and back, and the page already had every item, so it could put them in a
  different order out of what it was holding without asking anyone. Whether a sort sends a request is
  something you would have to look at, in the Network panel or the server log, rather than something
  the screen tells you.
- **credit:** full credit for saying a change on screen is no evidence that anything went to the
  server, because a request is a trip out to the server and back and the page can reorder what it
  already holds. Full credit for "the page can sort by itself". Do not accept a different quibble
  as the error: that sorting is slow, that the sort ought to be done on the server, or that they
  should have looked at the Network panel, unless the answer also says why the screen alone does
  not settle it.

### q-request-nothing-else-reaches

- **type:** mcq
- **goal:** w-request
- **move:** INTERPRET
- **answer:** 2
- **credit:** 1 has the server saving something it was never told about. 3 misreads the second
  request: adding a book reaches the server at the moment you add it, which is what the message
  says. 4 has the server starting a trip of its own, when every trip named here starts at the page,
  and the message names only two of them.
