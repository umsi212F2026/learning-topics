# CORS

Answer in two or three sentences, in your own words, with nothing open in front of you.

### q1

Your deployed React page asks your Express backend for the list of budgets, and the request fails. What is the difference between that failure being a CORS error and its being a server error?

### q4

Your Express backend refuses any request that doesn't carry a signed-in user's token. It also lists `https://tally.quay.app` as the one origin allowed under CORS. What is the difference between those two kinds of check?

### q2

A student writes in their team's notes:

"Now that CORS on our backend only allows our own site, nobody can call the backend with curl or Postman."

What is wrong with that?

### q3

Tally's React page at `https://tally.quay.app` fetches `https://tally.quay.app/budgets.json`, a file served alongside the page. The fetch fails, and a student says:

"CORS must have blocked it."

What is wrong with that?
