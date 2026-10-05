Pantrybook is a recipe box for a student housing co-op: members save recipes, tag them, and plan
the week's shared dinners. It runs on Fernlatch as two services in one project. `pantry-web`
builds the React frontend to static files and serves them at `https://pantry-web.fernlatch.io`;
`pantry-api`, the Express backend, answers at `https://pantry-api.fernlatch.io`. Its Postgres
database is a Fernlatch database in the same project. Each service builds and deploys on its own.
Fernlatch never stops `pantry-web`, but it stops `pantry-api` after 20 minutes with no requests
and starts it again on the next request, which takes up to about a minute. When a new deploy of
either service fails, Fernlatch keeps that service's previous version serving. Pantrybook has
been live and working for a month.

Each question is a separate incident on Pantrybook, independent of the others. Each gives one
line on what you did or noticed, then your coding agent's account of it, then a question. Answer
in two or three sentences.

### q1

**What you noticed:** I opened Pantrybook after lunch and the recipe list sat on its loading
spinner for a long while, then showed up as usual.

**Your agent's account:**

I pulled the last two hours of logs for `pantry-api` on Fernlatch. Deploy `#58` (your commit
`e40c7d1`) has been `Running` since Thursday.

```
12:02:44 GET /api/recipes 200 52ms
12:03:10 GET /api/recipes/112 200 18ms
12:23:11 Service idle for 20m; sleeping
13:41:05 Wake requested by incoming request
13:41:49 Server listening on port 8080
13:41:49 GET /api/recipes 200 61ms
13:42:03 GET /api/recipes?tag=vegan 200 37ms
```

There are no lines between 12:23 and 13:41. Your `GET /api/recipes` at 13:41:05 set off the wake,
and it was 44 seconds before the listener bound and that request returned. Every request since
has returned 200.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q2

**What you noticed:** I pushed a backend change that sorts recipes by when they were last cooked,
and Pantrybook still lists them in the old order.

**Your agent's account:**

Deploy `#61` of `pantry-api`, for your commit `7ab93e0`, has status `Health check timeout`.
Deploy `#60` is still `Running`, and Fernlatch kept routing all traffic to it throughout. The
build for `#61` ended:

```
added 214 packages in 9s
Build complete in 21s
```

Its runtime log:

```
15:20:03 > node server/index.js
15:20:04 pantry-api listening on port 3000
15:25:04 Health check GET /health on port 8080: no response after 300s
15:25:04 Stopping deploy #61
```

`server/config.js`, new in `7ab93e0`, sets the port to a fixed 3000 instead of reading `PORT`,
which Fernlatch sets to 8080. So `#61` listened on a port nothing was sent to, and it took no
traffic before Fernlatch stopped it.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q3

**What you noticed:** I tidied up the backend's environment variables on Fernlatch, and since then
Pantrybook shows no recipes.

**Your agent's account:**

I loaded `https://pantry-web.fernlatch.io` in a headless browser and pulled the request log for
`pantry-api` for the same minutes. Deploy `#60` is `Running`; saving the variables restarted it
at 09:12, and it has answered since.

`pantry-api`:

```
09:12:31 pantry-api listening on port 8080
09:14:07 GET /api/recipes 200 47ms
```

Browser console:

```
Access to fetch at 'https://pantry-api.fernlatch.io/api/recipes' from origin 'https://pantry-web.fernlatch.io' has been blocked by CORS policy: The 'Access-Control-Allow-Origin' header has a value 'https://pantry-web.fernlatch.app' that is not equal to the supplied origin.
```

`server/index.js` sets `Access-Control-Allow-Origin` from `WEB_ORIGIN`, which now reads
`https://pantry-web.fernlatch.app`, ending in `.app` where the page is served from `.io`. The 200
leaves `pantry-api` carrying that header, and the page's `fetch` rejects it.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q4

**What you noticed:** A housemate says that when she removes a tag from a recipe, the whole recipe
disappears.

**Your agent's account:**

`server/routes/tags.js`:

```
41  router.delete('/api/recipes/:id/tags/:tag', async (req, res) => {
42    await db.query('DELETE FROM recipes WHERE id = $1', [req.params.id]);
43    res.sendStatus(204);
44  });
```

Line 42 deletes from `recipes`, not from `recipe_tags`, and it ignores `:tag` entirely. So on the
deployed app every tag removal takes the whole recipe with it, which is what your housemate is
seeing on Pantrybook.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q5

**What you noticed:** I pushed a backend change that lets recipe search match ingredients as well
as titles, and searching for "lentils" still finds only recipes with lentils in the title.

**Your agent's account:**

I listed the deploys for `pantry-api` on Fernlatch. The newest, `#64`, for your commit `c3d8f15`,
has status `Errored`; `#63`, from Sunday, is `Running`. Output for `#64`:

```
==> Running build command 'npm ci'
npm ERR! code EUSAGE
npm ERR! `npm ci` can only install packages when your package.json and package-lock.json or npm-shrinkwrap.json are in sync. Please update your lock file with `npm install` before continuing.
npm ERR! Missing: fuse.js@7.0.0 from lock file
==> Build exited with code 1
```

`c3d8f15` adds `fuse.js` to `package.json` but doesn't include an updated `package-lock.json`, so
`npm ci` stopped before installing anything. Fernlatch ran nothing after that step for `#64`.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q6

**What you noticed:** Since yesterday, everyone in the house says Pantrybook shows an empty recipe
list.

**Your agent's account:**

I loaded `https://pantry-web.fernlatch.io` in a headless browser and captured its network
activity, then pulled the last three days of logs for `pantry-api` on Fernlatch.

Browser:

```
GET https://pantry-web.fernlatch.io/ 200
GET https://pantry-web.fernlatch.io/assets/index-4be81d.js 200
GET https://pantry-apl.fernlatch.io/api/recipes net::ERR_NAME_NOT_RESOLVED
```

`pantry-api`:

```
Oct 03 18:22:40 GET /api/recipes 200 44ms
Oct 03 18:40:12 error: duplicate key value violates unique constraint "recipes_slug_key"
Oct 03 18:40:12 POST /api/recipes 409 9ms
Oct 03 19:00:12 Service idle for 20m; sleeping
```

`VITE_API_URL` on `pantry-web` was edited yesterday morning and now reads
`https://pantry-apl.fernlatch.io`, with `apl` for `api`; the redeploy of `pantry-web` that the
edit set off baked it into the bundle, and that host name doesn't resolve. `pantry-api` has logged
nothing since Oct 03, including during my page load just now. The Oct 03 `duplicate key` line is
one recipe saved twice under the same name, answered with a 409.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.

### q7

**What you noticed:** I pushed a change that adds a "this week's dinners" page, and a housemate
says that page shows an error when she opens it.

**Your agent's account:**

Both services deployed your commit `5d02a7b` at 11:05: `pantry-web` `#40` and `pantry-api` `#65`
are `Running`. The build for `#65` ended:

```
npm WARN deprecated inflight@1.0.6: This module is not supported, and leaks memory.
added 231 packages in 11s
Build complete in 24s
```

`pantry-api` runtime log, last hour:

```
11:42:18 GET /api/recipes 200 49ms
11:42:31 GET /api/plans/week/2026-10-05 500 15ms
11:42:31 TypeError: Cannot read properties of undefined (reading 'map')
    at buildWeek (/app/server/routes/plans.js:33:24)
11:43:02 GET /api/recipes/87 200 21ms
```

`routes/plans.js:33` calls `plan.dinners.map`, and for a week with no plan saved yet the query
returns a `plan` with no `dinners`. Every `GET /api/plans/week/...` in the hour returns 500 at
that line; the recipe routes return 200. The `inflight` line is a deprecation notice for a package
another dependency pulls in.

From your agent's account, where did things go wrong, if they did, and what does someone visiting
the app right now see? If the account can't tell you, say why.
