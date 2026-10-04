# Rubric: backend

### q-define-backend

- **type:** free
- **goal:** w-backend
- **move:** DEFINE
- **answer:** the half of an app that doesn't run in the browser: a program of its own, running
  somewhere else (while you are developing, on your own laptop, at its own address), which the page
  sends requests to and which does the work the page can't do, such as reaching the database. The
  page is the other half.
- **credit:** full credit for saying it is the part of the app that runs outside the browser, as its
  own program, and answers what the page asks it. Full credit for "the part that runs on a server
  rather than in the browser, and handles the page's requests". Half credit for "the part the user
  doesn't see", which is also true of plenty of code that runs in the browser. Do not accept a bare
  "the server" or "the server side" with nothing more: naming where it runs is fine, but the answer
  also has to say what it does (answers the page's requests, does the work the page can't). Do not
  accept "the database", which is one of the things a backend talks to.

### q-backend-vs-dev-server

- **type:** free
- **goal:** w-backend
- **move:** DISTINGUISH
- **answer:** they answer different requests. The dev server hands your browser the page's own
  code (its HTML, JavaScript and CSS), the same files for everyone, and knows nothing about your
  books or your habits. The backend answers the requests the page sends once it is running: it does
  the work the page can't, and it is the only one of the two that reaches the database. The dev
  server is also a development convenience; when the app is deployed, something else takes over
  handing out the page's files, but the backend's job is still there.
- **credit:** full credit for the difference that matters: the dev server delivers the page's code
  to the browser, and the backend answers the running page's requests for data. Half credit for
  "they are on different ports", "one is Vite and one is my agent's code", or "the dev server goes
  away when you deploy", which are true and incidental. Do not accept "they are the same thing under
  two names", and do not accept an answer in which the dev server's job is to pass the page's
  requests on to the backend.

### q-backend-in-the-browser

- **type:** free
- **goal:** w-backend
- **move:** CATCH
- **answer:** a backend is not a part of the page's code. It is a separate program running outside
  the browser, at an address of its own, that the page sends requests to. Code inside the page, even
  the part furthest from the buttons, is still the front half of the app, and an app that does
  everything in the browser has no backend at all.
- **credit:** full credit for saying a backend runs outside the browser as its own program, so code
  inside the page is not a backend however hidden it is. Do not accept a different quibble as the
  error: that they ought to add a backend, that their app is too small to need one, or that a
  browser is a slow place to do work. An answer that says only "you need a database too" has not
  named the error.
