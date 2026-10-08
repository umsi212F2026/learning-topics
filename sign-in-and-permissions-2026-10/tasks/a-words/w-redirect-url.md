# Redirect URL

Answer in two or three sentences, in your own words, with nothing open in front of you.

Pantry is a recipe box for a campus cooking club, with sign-in through GitHub. Its React frontend
is on Pagecove, a static host, at `https://pantry.pagecove.app`, and its Express backend is on
Rivetbox, a server host, at `https://pantry-api.rivetbox.com`. On a laptop, the backend runs at
`http://localhost:3001`.

### q2

A student says:

"Pantry's redirect URL is `https://pantry.pagecove.app`, since that's the address people type to
get to the app."

What is wrong with that?

### q3

When the student registered Pantry with GitHub, they entered
`http://localhost:3001/auth/github/callback` as the redirect URL, and sign-in works on their laptop.
Now they are deploying, and they say:

"The redirect URL is just a setting in our backend code. To make sign-in work on the live app, all I
need to do is set it to `https://pantry-api.rivetbox.com/auth/github/callback` in Rivetbox's
settings."

What is wrong with that?

### q1

What is the difference between Pantry's redirect URL and Pantry's own URL?
