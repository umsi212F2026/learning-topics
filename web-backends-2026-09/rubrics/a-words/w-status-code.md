# Rubric: status code

### q-status-vs-error-message

- **type:** free
- **goal:** w-status-code
- **move:** DISTINGUISH
- **answer:** the status code is a number that comes back with every response, successful ones
  included, and it says in a standard way how the request went, so the page can act on it without
  reading any words. The message is wording chosen by whoever built the server, for a person to read,
  and a response may not carry one at all.
- **credit:** full credit for the difference that matters: the code is a standard number that comes
  with every response and says how it went, while the message is optional wording meant for a person.
  Full credit for "every response has a code, even a successful one, and only some have a message".
  Half credit for "one is a number and one is words" on its own. Do not accept "the status code only
  appears when something goes wrong", which is the confusion itself, and do not accept "the message
  has more detail" as the whole difference.

### q-status-only-on-errors

- **type:** free
- **goal:** w-status-code
- **move:** CATCH
- **answer:** every response carries a status code, whether things went well or not. A successful
  save comes back with one too, a 200 or a 201, and that is how the page knows it worked. The codes
  in the 400s and 500s are the ones that report trouble, but they are not the only codes there are.
- **credit:** full credit for saying every response has a code, and that a successful one carries a
  code saying it succeeded. Naming 200 or 201 is a good addition and is not required. Do not accept a
  different quibble as the error: that the page might not look at the code, that the agent should log
  it, or that 404 means something else.

### q-status-404-on-fetch

- **type:** mcq
- **goal:** w-status-code
- **move:** INTERPRET
- **answer:** 4
- **credit:** 1 and 2 both say the server never received the request, when a status code is itself
  the server's answer, so getting one means the request got there. 2 also takes the number for the
  browser's. 3 gives the number to the page, when the page only receives it.
