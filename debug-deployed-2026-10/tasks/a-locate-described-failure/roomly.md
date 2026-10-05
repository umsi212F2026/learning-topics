Roomly is a study-room finder for a university library: students search for free rooms and book
one for an hour. Its React frontend is built to static files and served by Pagewell, a
static-site host, at `https://roomly.pagewell.app`. Its Express backend, `roomly-api`, runs on
Kettlerun at `https://roomly-api.kettlerun.net`, and its Postgres database is on Kettlerun too.
Kettlerun stops a backend that has had no requests for 15 minutes and starts it again on the next
request, which takes up to about a minute. When a new deploy fails on either host, that host keeps
the previous version serving. Roomly has been live and working for several weeks.

Each question is a separate incident on Roomly, independent of the others. Each gives one
line on what you did or noticed, then your coding agent's account of it, then a question. Answer
in two or three sentences.

### q1

**What you noticed:** I pushed a change that adds a building filter to the search page, and an
hour later I still don't see it on Roomly.

**Your agent's account:**

I listed the deploys for the `roomly` site on Pagewell. The newest, for your commit `3e7b0d4`, has
status `HALTED`; the one before it, `c18f9a2` from last Tuesday, is `PUBLISHED`. Output for
`3e7b0d4`:

```
> roomly-web@1.0.0 build
> vite build
vite v5.4.2 building for production...
transforming (41) src/pages/Search.jsx
[vite]: Rollup failed to resolve import "./BuildingFilter" from "src/pages/Search.jsx".
Error: Process exited with code 1
```

`Search.jsx` imports `./BuildingFilter`, but the component is at
`src/components/BuildingFilter.jsx`, so the relative path points at a file that isn't in the
commit. Pagewell stopped `3e7b0d4` at that step, and its log has nothing after it.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q2

**What you noticed:** A friend says that when she clicks Book on a room, nothing happens.

**Your agent's account:**

I pulled the last hour of runtime logs for `roomly-api` on Kettlerun. Deploy `d-4821` (your commit
`a91f3c2`) has been `ACTIVE` since yesterday at 16:02.

```
14:31:07 GET /api/rooms 200 38ms
14:31:12 POST /api/bookings 500 12ms
14:31:12 TypeError: Cannot read properties of undefined (reading 'roomId')
    at /app/server/routes/bookings.js:27:31
14:31:40 GET /api/rooms?building=library 200 41ms
```

The handler at `routes/bookings.js:27` dereferences `req.body.slot.roomId`, and `slot` is
undefined on these requests. Every `POST /api/bookings` in the window throws there; every other
route returns 200.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q3

**What you noticed:** I opened Roomly on my phone to show a friend, and the room list is empty.

**Your agent's account:**

I loaded `https://roomly.pagewell.app` in a headless browser and captured its network activity,
then pulled the request log for `roomly-api` on Kettlerun for the same minutes.

Browser:

```
GET https://roomly.pagewell.app/ 200
GET https://roomly.pagewell.app/assets/index-9f2c1a.js 200
GET http://localhost:3001/api/rooms net::ERR_CONNECTION_REFUSED
```

Kettlerun, `roomly-api`, 19:02 to 19:10:

```
19:04:00 GET /healthz 200 2ms
19:09:00 GET /healthz 200 2ms
```

The bundle Pagewell is serving has `http://localhost:3001` as its API base: `VITE_API_URL` isn't
set in the Pagewell site's environment, so `src/api.js` fell back to its default. The only hits on
`roomly-api` in that window are Kettlerun's own health checks; no `/api/rooms`.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q4

**What you noticed:** This morning I opened Roomly and the room list took ages to show up, then
everything was fine.

**Your agent's account:**

I pulled the last 24 hours of logs for `roomly-api` on Kettlerun. Deploy `d-4821` has been
`ACTIVE` throughout.

```
Oct 04 22:47:15 Error: connect ETIMEDOUT 10.4.0.12:5432
Oct 04 22:47:16 GET /api/rooms 200 1310ms
Oct 04 23:04:02 Instance idle 15m, suspending
Oct 05 08:51:37 Instance resuming for incoming request
Oct 05 08:52:19 Server listening on port 10000
Oct 05 08:52:20 GET /api/rooms 200 96ms
Oct 05 08:52:31 GET /api/rooms?building=science 200 41ms
```

Last night's `ETIMEDOUT` is a single database connection timeout that the retry recovered from, ten
hours before you opened the app. This morning, your first `/api/rooms` hit triggered the resume at
08:51:37, and the 42 seconds until the listener bound is the delay you saw. Everything since has
returned 200.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q5

**What you noticed:** I renamed the backend's `DB_URL` environment variable to `DATABASE_URL` in
Kettlerun's settings, and now the room list won't load.

**Your agent's account:**

I checked `roomly-api` on Kettlerun. Saving the environment change restarted the current deploy,
`d-4821`, in place. A settings restart isn't a new deploy, so Kettlerun keeps no other copy running
while it happens. Status is `RESTARTING (attempt 6)`. The runtime log repeats about every 30
seconds:

```
14:10:02 > node server/index.js
14:10:03 Error: DB_URL is not set
    at Object.<anonymous> (/app/server/db.js:4:9)
14:10:03 Exited with status 1
14:10:33 > node server/index.js
14:10:34 Error: DB_URL is not set
    at Object.<anonymous> (/app/server/db.js:4:9)
14:10:34 Exited with status 1
```

Meanwhile Kettlerun's edge answers requests to `roomly-api.kettlerun.net` with
`503 Service Unavailable`. `server/db.js` throws at line 4 when `DB_URL` is missing, and that runs
before `app.listen`.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q6

**What you noticed:** A friend says she gets an error on Roomly when she books a room for 9 in the
morning.

**Your agent's account:**

I reproduced it. A booking for 9:00:

```
[server] Listening on http://localhost:3001
[server] POST /api/bookings 500 4ms
[server] RangeError: Invalid time value
    at Date.toISOString (<anonymous>)
    at /Users/you/roomly/server/routes/bookings.js:41:38
```

`server/routes/bookings.js:41` builds the start time as `${date}T${hour}:00`, so 9 becomes `T9:00`,
which `new Date` rejects; two-digit hours parse fine. That's what is throwing on the deployed
`/api/bookings` for your friend.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q7

**What you noticed:** I pushed a backend change that tidies up its middleware, and now the room
list on Roomly is empty.

**Your agent's account:**

Deploy `d-4907`, for your commit `b52e11a`, is `ACTIVE` on Kettlerun. I loaded
`https://roomly.pagewell.app` in a headless browser and pulled the request log for `roomly-api`
for the same minute.

Kettlerun, `roomly-api`:

```
10:14:22 GET /api/rooms 200 44ms
```

Browser console:

```
Access to fetch at 'https://roomly-api.kettlerun.net/api/rooms' from origin 'https://roomly.pagewell.app' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
GET https://roomly-api.kettlerun.net/api/rooms net::ERR_FAILED 200 (OK)
```

`b52e11a` removed the middleware line in `server/index.js` that set `Access-Control-Allow-Origin`
to `FRONTEND_ORIGIN`, so the 200 goes out without that header and the page's `fetch` rejects.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.
