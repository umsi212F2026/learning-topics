# status code

### q-status-vs-error-message

Your agent says that an Add with an empty box comes back with a 400 and the message "An item needs
some text". What is the difference between the status code and the message?

### q-status-only-on-errors

A classmate says: "My Add worked and the book was saved, so that response had no status code.
Status codes only turn up when something goes wrong." What is wrong with what they said?

### q-status-404-on-fetch

You open a book in Shelf that another tab deleted a moment ago. The page asks the server for that
book, and the response comes back with 404, the code for "nothing found at that address". Which of
these is true?

1. The request got lost on the way, so the server never received it.
2. The request never got to the server, and the browser reported a 404.
3. The page decided the book was gone, and 404 is how it reports that.
4. The server got the request and answered that the book wasn't there.
