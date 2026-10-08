Huddle is your Problem Set 3 app: the trip board for a college hiking club. Members post the day
trips they're leading, with a date and a meeting point, and other members sign up. The day before
a trip, Huddle emails each member signed up for it a reminder with the meeting point. Its React
frontend is built to static files on Leafhost, at `https://huddle.leafhost.app`, and its Express
backend runs on Dockyard, at `https://huddle-api.dockyard.run`, with a Postgres database. Sign-in
through Google already works.

The backend's routes:

- `GET /api/trips` lists the upcoming trips, with their meeting points.
- `POST /api/trips` posts a new trip; whoever posts it leads it.
- `PATCH /api/trips/:id` changes a trip's date, meeting point or number of places.
- `DELETE /api/trips/:id` cancels a trip.
- `POST /api/trips/:id/signups` signs the signed-in member up for a trip.
- `DELETE /api/trips/:id/signups` takes the signed-in member off a trip.
- `GET /api/me` returns the signed-in member's name and picture.

The app has three levels: a signed-in member, who may see the trips, post one and sign up; the
leader of a trip, the member who posted it, who may change or cancel it; and the club's officers,
who may change or cancel any trip.

You and your coding agent are giving Huddle its rules for who may do what. Each question below
shows two versions, A and B, of one piece of that work. The questions are independent: treat each
one as if it were the only one you had seen. For each, answer in two or three sentences: would you
agree to A, B, or both? What gives it away?

### q1

Your agent offers two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Signed-in member | Leader of the trip | Officer | Not signed in |
| ------ | ---------------- | ------------------ | ------- | ------------- |
| See the trips | yes | yes | yes | no |
| Post a trip | yes | yes | yes | no |
| Sign up for a trip | yes | yes | yes | no |
| Leave a trip | yes | yes | yes | no |
| Change a trip | no | yes | yes | no |
| Cancel a trip | no | yes | yes | no |

**B**

| Action | Signed-in member | Leader of the trip | Officer |
| ------ | ---------------- | ------------------ | ------- |
| See the trips | yes | yes | yes |
| Post a trip | yes | yes | yes |
| Sign up for a trip | yes | yes | yes |
| Leave a trip | yes | yes | yes |
| Change a trip | no | yes | yes |
| Cancel a trip | no | yes | yes |

> This covers everyone who uses Huddle.

Would you agree to A, B, or both? What gives it away?

### q2

Your agent offers two versions of the who-may-do-what table for `DEPLOY.md`.

**A**

| Action | Signed-in member | Leader of the trip | Officer | Not signed in |
| ------ | ---------------- | ------------------ | ------- | ------------- |
| See the trips | yes | yes | yes | no |
| Post a trip | yes | yes | yes | no |
| Sign up for a trip | yes | yes | yes | no |
| Change a trip | no | yes | yes | no |
| Cancel a trip | no | yes | yes | no |

**B**

| Action | Signed-in member | Leader of the trip | Officer | Not signed in |
| ------ | ---------------- | ------------------ | ------- | ------------- |
| See the trips | yes | yes | yes | no |
| Post a trip | yes | yes | yes | no |
| Sign up for a trip | yes | yes | yes | no |
| Leave a trip | yes | yes | yes | no |
| Change a trip | no | yes | yes | no |
| Cancel a trip | no | yes | yes | no |

Would you agree to A, B, or both? What gives it away?

### q3

Your agent offers two versions of one step of its plan.

**A**

> Step 3. On the trip page, show the Change and Cancel buttons only to the trip's leader and to
> officers.

**B**

> Step 3. On the trip page, show the Change and Cancel buttons only to the trip's leader and to
> officers. On `PATCH` and `DELETE /api/trips/:id`, the server also loads the trip and refuses the
> request from anyone but its leader or an officer.

Would you agree to A, B, or both? What gives it away?

### q4

Your agent offers two versions of the backend's route list. `requireAuth` refuses any request with
no signed-in member; `requireLeaderOrOfficer` refuses anyone but the trip's leader or an officer.

**A**

```js
router.get('/api/trips', requireAuth, listTrips);
router.post('/api/trips', requireAuth, createTrip);
router.patch('/api/trips/:id', requireAuth, requireLeaderOrOfficer, updateTrip);
router.delete('/api/trips/:id', requireAuth, requireLeaderOrOfficer, cancelTrip);
router.post('/api/trips/:id/signups', requireAuth, signUp);
router.delete('/api/trips/:id/signups', requireAuth, leaveTrip);
router.get('/api/me', requireAuth, getMe);
```

**B**

```js
router.get('/api/trips', requireAuth, listTrips);
router.post('/api/trips', requireAuth, createTrip);
router.patch('/api/trips/:id', requireAuth, requireLeaderOrOfficer, updateTrip);
router.delete('/api/trips/:id', requireAuth, requireLeaderOrOfficer, cancelTrip);
router.post('/api/trips/:id/signups', requireAuth, signUp);
router.delete('/api/trips/:id/signups', leaveTrip);
router.get('/api/me', requireAuth, getMe);
```

Would you agree to A, B, or both? What gives it away?

### q5

Your agent offers two versions of the handler for `DELETE /api/trips/:id/signups`, which runs
after `requireAuth`.

**A**

```js
async function leaveTrip(req, res) {
  const userId = req.session.userId;
  await db.query(
    'DELETE FROM signups WHERE trip_id = $1 AND user_id = $2',
    [req.params.id, userId]
  );
  res.status(204).end();
}
```

**B**

```js
async function leaveTrip(req, res) {
  const userId = req.get('X-User-Id');
  await db.query(
    'DELETE FROM signups WHERE trip_id = $1 AND user_id = $2',
    [req.params.id, userId]
  );
  res.status(204).end();
}
```

Would you agree to A, B, or both? What gives it away?

### q6

Your agent offers two versions of its plan for enforcing the rules. Each starts with the `users`
table, then gives the same three lines.

**A**

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  google_sub TEXT UNIQUE NOT NULL,
  name TEXT NOT NULL,
  email TEXT NOT NULL,
  picture TEXT,
  role TEXT NOT NULL DEFAULT 'member'
);
```

**B**

```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  google_sub TEXT UNIQUE NOT NULL,
  name TEXT NOT NULL,
  picture TEXT,
  role TEXT NOT NULL DEFAULT 'member'
);
```

**Both continue:**

> 1. `requireAuth` runs on every route, and refuses a request with no signed-in member.
> 2. On `PATCH` and `DELETE /api/trips/:id`, `requireLeaderOrOfficer` loads the trip and refuses
>    the request unless the session's user leads it or has the `officer` role.
> 3. Every handler takes the user from `req.session.userId`.

Would you agree to A, B, or both? What gives it away?

### q7

Your agent reports that the rules are in place. It offers two ways to confirm that someone who
isn't signed in can't see the trips and their meeting points.

**A**

> Sign out, open `https://huddle.leafhost.app` in the browser, and check that it shows the sign-in
> button instead of the list of trips.

**B**

> From a terminal, with no session cookie, send `GET https://huddle-api.dockyard.run/api/trips`.

Would you agree to A, B, or both? What gives it away, and what should the request you chose get
back?

### q8

Your agent reports that the rules are in place. It offers two ways to confirm that only a trip's
leader or an officer can cancel it. Trip 4 was posted from your own account, which isn't an
officer.

**A**

> From a terminal, with the session cookie of a second account that isn't an officer, send
> `DELETE /api/trips/4`.

**B**

> From a terminal, with no session cookie, send `DELETE /api/trips/4`.

Would you agree to A, B, or both? What gives it away, and what should the request you chose get
back?
