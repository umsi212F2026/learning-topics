# Rubric: production

What it names: the copy of the app that real users use, along with its data. Nearest confusable:
development. Synonyms: prod, live.

### q-catch-production-localhost

- **goal:** `w-production`
- **move:** CATCH
- **answer:** production is the copy of the app that real users use, with their data. An app
  running on your laptop at localhost is development: only you can reach it, and its database holds
  your testing, not users' data. Working on localhost says nothing about whether a production copy
  exists.
- **credit:** full for naming the actual error: what runs on their laptop is their development copy,
  which no real user reaches, so it is not production. Half for "localhost only works on your
  machine" with nothing about production being the copy real users use. Do not accept a different
  quibble: "they haven't tested it enough", or "production needs Postgres".

### q-define-production

- **goal:** `w-production`
- **move:** DEFINE
- **answer:** the copy of the app that real users use, running on a host they can reach, together
  with the data they put into it. It is kept apart from the copy you change and test on your laptop.
- **credit:** full for the copy of the app real users use, with its own data, as against the one you
  work on. Half for "the app deployed on a server" or "the public version" with nothing about its
  being what real users use. Do not accept "prod" or "the live version" alone, which name it again.
