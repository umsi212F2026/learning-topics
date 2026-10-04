# Rubric: API

### q-define-api

- **type:** free
- **goal:** w-api
- **move:** DEFINE
- **answer:** the set of requests the server has promised to answer, each with what you send it and
  what comes back: give me all the books, save this new book, change whether this one is finished,
  delete this one. Each of those is one of the server's endpoints, so the API is its endpoints
  together with the promise about what each one takes and returns. It is the agreement the page is
  written against rather than a piece of the app you could point at.
- **credit:** full credit for saying it is the set of requests the server promises to answer, or what
  the page is allowed to ask for and what comes back. Full credit for "the list of things the page
  can ask the server to do". Full credit for "the server's endpoints and what each one takes and
  returns". Half credit for "the list of endpoints" with nothing about what goes in or comes back.
  Half credit for "how the page and the server talk to each other", with nothing about a set of
  requests settled in advance. Do not accept "the backend" or "the server",
  which is the thing that answers rather than what has been promised, and do not accept "the code
  that handles the requests".

### q-api-vs-backend

- **type:** free
- **goal:** w-api
- **move:** DISTINGUISH
- **answer:** the backend is the running program: something on your laptop with a process, a
  terminal it prints to, and a database behind it. The API is what that program has promised to
  answer: the set of requests, each with what it takes and what it gives back. One is the machinery
  and the other is the agreement it keeps, so everything inside the backend can be rewritten with the
  API left exactly as it was.
- **credit:** full credit for the difference that matters: the backend is the running thing, and the
  API is the set of requests it promises to answer. Saying that the inside can change without the
  API changing shows it well but is not required. Half credit for "the API is part of the backend"
  with nothing about what is promised. Do not accept "the API is the front end", "the API is a
  second server", or a difference of size.

### q-api-as-a-stop

- **type:** free
- **goal:** w-api
- **move:** CATCH
- **answer:** the API is not a stop on the way. It is the set of requests the server has promised to
  answer, so the page's request goes to the server, at one of its endpoints. "The page sends a
  request to the server's API" would have been fine; making the API something that takes the book and
  hands it on gives it a part it does not have.
- **credit:** full credit for saying the API is not a part the request passes through but the set of
  requests the server answers, so the page's request goes straight to the server. Half credit for an
  answer that only denies the extra stop without saying what an API is. Do not accept a different
  quibble as the error: that the way back to the page is missing, that the database has to answer the
  server, or that they should have named the endpoint.
