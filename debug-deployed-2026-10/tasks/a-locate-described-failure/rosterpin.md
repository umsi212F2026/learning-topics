Rosterpin is a sign-up sheet for a campus climbing club: members see upcoming trips and put their
name down for a seat in one of the cars. Its React frontend is built to static files and served by
Glintpage, a static-site host, at `https://rosterpin.glintpage.site`. Its Express backend,
`rosterpin-api`, runs on Moorbolt at `https://rosterpin-api.moorbolt.dev`, and its Postgres
database is on Moorbolt too. Moorbolt stops a backend after 10 minutes with no requests and starts
it again on the next request, which takes up to about half a minute. When a new deploy's build
fails, both hosts leave the previous version serving. When a new backend deploy's build succeeds,
Moorbolt stops the running version first and then starts the new one, so if the new one doesn't
start, nothing is serving the backend until a later deploy does. Rosterpin has been live and
working since the start of term, except in a question whose own line says it is the first deploy.

Each question is a separate incident on Rosterpin, independent of the others. Each gives one line
on what you did or noticed, then your coding agent's account of it, then a question. Answer in two
or three sentences.

### q1

**What you noticed:** A club member says that when she opens the Saturday trip, the page shows
"Something went wrong".

**Your agent's account:**

I pulled the last hour of runtime logs for `rosterpin-api` on Moorbolt. Release `r-219` (your
commit `4c6e0b8`) has been `serving` since Monday.

```
16:05:12 GET /api/trips 200 33ms
16:05:20 GET /api/trips/48/seats 500 7ms
16:05:20 TypeError: Cannot read properties of null (reading 'capacity')
    at /app/server/routes/seats.js:19:31
16:05:41 GET /api/trips/51/seats 200 26ms
```

`routes/seats.js:19` reads `car.capacity`, and trip 48 (Saturday's) points at a car whose row was
deleted last week, so the lookup gives `null` there. Every request for trip 48's seats in the hour
returns 500 at that line; the trip list and other trips' seats return 200.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q2

**What you noticed:** I pushed a backend change that upgrades its packages and tidies up
`server/index.js`, and now Rosterpin shows no trips.

**Your agent's account:**

Release `r-224` of `rosterpin-api`, for your commit `91fd2a3`, is `serving` on Moorbolt. Its build
output ended:

```
npm WARN deprecated rimraf@3.0.2: Rimraf versions prior to v4 are no longer supported
added 187 packages in 8s
build ok
```

I loaded `https://rosterpin.glintpage.site` in a headless browser and pulled the request log for
`rosterpin-api` for the same minute.

Moorbolt, `rosterpin-api`:

```
20:31:09 GET /api/trips 200 29ms
```

Browser console:

```
Access to fetch at 'https://rosterpin-api.moorbolt.dev/api/trips' from origin 'https://rosterpin.glintpage.site' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

The tidy-up in `91fd2a3` moved the `app.use(cors(...))` line in `server/index.js` below the
routes, so `/api/trips` sends its 200 before that middleware runs, without an
`Access-Control-Allow-Origin` header, and the page's `fetch` rejects it. The `rimraf` line is a
deprecation notice for a package the build tools pull in.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q3

**What you noticed:** I pushed a backend change that emails a reminder the night before each trip,
and now Rosterpin shows no trips.

**Your agent's account:**

Release `r-226` of `rosterpin-api`, for your commit `0e7c5d9`, has status `exited`. Moorbolt
stopped `r-225` when `r-226`'s build finished, and no release is `serving`. Runtime log:

```
09:02:41 > node server/index.js
09:02:41 Error: Cannot find module 'nodemailer'
09:02:41 Require stack:
09:02:41 - /app/server/reminders.js
09:02:41 - /app/server/index.js
09:02:41 Exited with status 1
```

Since 09:02, requests to `rosterpin-api.moorbolt.dev` get Moorbolt's own `502 Bad Gateway`.
`0e7c5d9` requires `nodemailer` in `server/reminders.js`, but `package.json` lists it under
`devDependencies`, and Moorbolt installs production dependencies only.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q4

**What you noticed:** I showed Rosterpin at the club meeting tonight, and the trip list took a
while to appear the first time; after that it was quick.

**Your agent's account:**

I pulled tonight's logs for `rosterpin-api` on Moorbolt. Release `r-219` has been `serving` since
Monday.

```
18:12:40 GET /api/trips 200 31ms
18:22:41 no traffic for 10m, scaling to zero
19:47:02 request received, scaling to one
19:47:29 rosterpin-api listening on port 4000
19:47:29 GET /api/trips 200 58ms
19:47:35 GET /api/trips/52/seats 200 22ms
19:48:10 GET /api/trips 200 27ms
```

From 18:22 to 19:47 there were no instances. The request at 19:47:02 brought one up, and 27
seconds passed before the listener bound and that first `/api/trips` returned. Every request
since has returned 200 in under 60ms.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q5

**What you noticed:** A club member says Rosterpin let five people sign up for a car with four
seats.

**Your agent's account:**

I've confirmed what is happening with sign-ups on the live site. `server/routes/seats.js`:

```
52  const taken = Number((await db.query(
53    'SELECT count(*) FROM seats WHERE car_id = $1', [carId])).rows[0].count);
54  if (taken > car.capacity) {
55    return res.status(409).json({ error: 'Car full' });
56  }
```

Line 54 uses `>` where it needs `>=`, so a car with all four seats taken still accepts a fifth.
Rosterpin is taking one sign-up past capacity on every car, and that is what your member saw.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q6

**What you noticed:** This is the first time I've deployed Rosterpin. I pushed it to both hosts
this afternoon and sent the club the link to the site.

**Your agent's account:**

On Moorbolt, release `r-1` of `rosterpin-api` is `serving`, and `GET /healthz` returns 200. On
Glintpage, the `rosterpin` site has a single deploy, for your commit `a07d3be`, with status
`errored`; there are no earlier deploys. Its output:

```
> rosterpin-web@0.1.0 build
> vite build
vite v5.4.8 building for production...
[vite:esbuild] Transform failed with 1 error:
/build/src/pages/Trips.jsx:27:6: ERROR: Unexpected closing "div" tag does not match opening "section" tag
Error: Process exited with code 1
```

`src/pages/Trips.jsx` opens a `<section>` at line 12 and closes it with `</div>` at line 27.
Glintpage stopped `a07d3be` at that step, and its log has nothing after it.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q7

**What you noticed:** A member says Rosterpin's trip list has been empty since last week.

**Your agent's account:**

I loaded `https://rosterpin.glintpage.site` in a headless browser and captured its network
activity, then checked `rosterpin-api` on Moorbolt for the same minutes.

Browser:

```
GET https://rosterpin.glintpage.site/ 200
GET https://rosterpin.glintpage.site/assets/index-c27e90.js 200
GET https://rosterpin-server.moorbolt.dev/api/trips net::ERR_NAME_NOT_RESOLVED
```

Moorbolt, at 13:26:

```
$ moorbolt status rosterpin-api
release r-219  serving  instances: 0  last request: 12:31:07
```

The bundle Glintpage is serving calls `rosterpin-server.moorbolt.dev`, the backend's name before
you renamed it to `rosterpin-api` last Tuesday; Moorbolt released the old name, so it no longer
resolves. `VITE_API_URL` on Glintpage still holds it. Nothing has arrived at `rosterpin-api` since
12:31, including during my page load just now.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.
