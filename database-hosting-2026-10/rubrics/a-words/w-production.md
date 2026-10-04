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

### q-production-vs-development

- **goal:** `w-production`
- **move:** DISTINGUISH
- **answer:** who uses it, and whose data it holds. Production is the copy of the app that real
  users use, along with their data: what they add there is the app's real record. Development is
  the copy you work on and try changes in, usually on your laptop, and its data is only what you
  put there while building and testing. A mistake in development costs you some test rows; a
  mistake in production reaches users and their data.
- **credit:** full for the difference that matters: production is the copy real users use, with
  their data, and development is the copy you build and try things in, with data only you put
  there. Half for "production is on the host and development is on my laptop" with nothing about
  who uses each or whose data it holds. Do not accept "production uses Postgres and development
  uses SQLite", "production has no bugs", or a difference of speed.
