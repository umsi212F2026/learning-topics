# Rubric: endpoint

### q-define-endpoint

- **type:** free
- **goal:** w-endpoint
- **move:** DEFINE
- **answer:** one of the addresses the server answers at, standing for one thing the page can ask it
  to do: here, an address the page can send a delete to. A server answers at several of them, each
  with its own job, and the page picks the one that matches what it wants.
- **credit:** full credit for saying it is one address the server answers at, tied to one thing the
  page can ask for. Full credit for "one of the addresses the page sends its requests to, each doing
  a different job". Half credit for "a place the page sends requests" with nothing about its being an
  address or about there being several, one per job. Do not accept "an API route", which is another
  name for it, and do not accept "the server's address" on its own, which is where the server is
  rather than one of the things it answers.

### q-endpoint-vs-page-address

- **type:** free
- **goal:** w-endpoint
- **move:** DISTINGUISH
- **answer:** a page's address is meant for a person: you type it in and the browser shows you
  something to look at. An endpoint is meant for the running page: the page sends its requests there
  and gets back data to work with, not a page to look at. Both are addresses, and in an app you are
  developing the page and the endpoints usually sit at two different addresses on your laptop.
- **credit:** full credit for saying an endpoint is an address the page's own code sends requests to
  and gets data back from, while a page's address is one a person opens to see something. Half credit
  for "one is for the server and one is for the browser", which gets the pairing roughly right with
  nothing about who does the asking or what comes back. Do not accept "an endpoint is not a real
  address" or "you can't open an endpoint in a browser": you can, and what comes back is data rather
  than the app.

### q-endpoint-opened-in-browser

- **type:** free
- **goal:** w-endpoint
- **move:** CATCH
- **answer:** that address is one of the server's endpoints, and answering it with data is exactly
  what it is for. The text in braces is the list of items the page normally asks for and draws.
  Nothing is broken, and the app itself is at the page's own address, which is a different one.
- **credit:** full credit for saying an endpoint answers with data rather than with a page, so what
  they saw is the server working as intended. Saying the app is at the page's own address is a good
  addition and is not required. Do not accept a different quibble as the error: that they typed the
  address wrongly, that the server ought to answer with a page, or that they should have used the
  Network panel. An answer that agrees something is broken has not found the error.
