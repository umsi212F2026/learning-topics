Ridepool is your Problem Set 3 app: a carpool board for a university hiking club, where members who
are driving out to a hike offer the seats in their car, and other members join a ride. Riders see
the driver's email so they can arrange the pickup. Its React frontend is built to static files on
Glasspost, at `https://ridepool.glasspost.app`, and its Express backend runs on Burrowhost, at
`https://ridepool-api.burrowhost.com`, with a Postgres database. Sign-in through Google already
works: once someone signs in, the backend keeps them signed in with a session cookie. Now you and
your coding agent are deciding who may do what.

The backend's routes:

- `GET /api/rides`: lists every upcoming ride.
- `POST /api/rides`: offers a ride; whoever offers it is its driver.
- `PATCH /api/rides/:id`: edits a ride's departure time, meeting spot or number of seats.
- `DELETE /api/rides/:id`: cancels a ride.
- `POST /api/rides/:id/riders`: adds the signed-in user to a ride's riders.
- `GET /api/me`: returns the signed-in user's id, Google name and picture.

The app's levels: a **signed-in member**; the **driver** of a ride, the member who offered it; and
a **trip leader**, one of the club's trip leaders, who look after the whole board.

Each question below is a separate piece of the work. They are independent: treat each one as if
it were the only one you had seen. Answer each in two to four sentences.

### draft-table

Your agent drafts this table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Driver of the ride | Trip leader |
| --- | --- | --- | --- | --- |
| See the rides | yes | yes | yes | yes |
| Offer a ride | no | yes | yes | yes |
| Edit a ride | no | no | yes | yes |
| Cancel a ride | no | no | yes | yes |
| See your own name and picture | no | yes | yes | yes |

Would you agree to this as it stands? If not, what would you change?

### edit-ride

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Driver of the ride | Trip leader |
| --- | --- | --- | --- | --- |
| See the rides | yes | yes | yes | yes |
| Offer a ride | no | yes | yes | yes |
| Edit a ride | no | no | yes | yes |
| Cancel a ride | no | no | yes | yes |
| Join a ride | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. Add `requireAuth` in `backend/middleware/auth.js`, which refuses any request from someone not
   signed in. Put it on every route that changes data, and on `GET /api/me`.
2. Add a `role` column to `users`, `'member'` by default. You set `'leader'` by hand for the trip
   leaders.
3. In `DELETE /api/rides/:id`, load the ride and refuse the request unless the signed-in user is
   its driver or a trip leader.
4. In React, the Edit button on a ride shows only to its driver and to trip leaders:
   `{(user.id === ride.driverId || user.role === 'leader') && <EditRideButton />}`.
5. `PATCH /api/rides/:id` runs `requireAuth` and then saves whatever new time, meeting spot or
   seat count it is sent.
6. In React, show the Cancel button only to the ride's driver and to trip leaders.

Would you agree to this as it stands? If not, what would you change?

### who-is-asking

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Driver of the ride | Trip leader |
| --- | --- | --- | --- | --- |
| See the rides | yes | yes | yes | yes |
| Offer a ride | no | yes | yes | yes |
| Edit a ride | no | no | yes | yes |
| Cancel a ride | no | no | yes | yes |
| Join a ride | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. `requireAuth` refuses any request from someone not signed in. It goes on every route that
   changes data, and on `GET /api/me`.
2. Add a `role` column to `users`, `'member'` by default. You set `'leader'` by hand for the trip
   leaders.
3. So the backend knows who is asking, React's fetch helper adds `userId` to the JSON body of every
   request that changes data, set to the id that `GET /api/me` returned.
4. `requireDriverOrLeader`, on `PATCH` and `DELETE /api/rides/:id`, loads the ride and the user
   with the id in `req.body.userId`, and refuses the request unless that user is the ride's driver
   or a trip leader.
5. `createRide` records `req.body.userId` as the new ride's driver, and `joinRide` adds
   `req.body.userId` to the ride's riders.
6. In React, show the Edit and Cancel buttons only to the ride's driver and to trip leaders.

Would you agree to this as it stands? If not, what would you change?

### routes-file

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Driver of the ride | Trip leader |
| --- | --- | --- | --- | --- |
| See the rides | yes | yes | yes | yes |
| Offer a ride | no | yes | yes | yes |
| Edit a ride | no | no | yes | yes |
| Cancel a ride | no | no | yes | yes |
| Join a ride | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. `requireAuth` refuses the request unless `req.session.userId` is set.
2. `requireDriverOrLeader` loads the ride and refuses the request unless
   `ride.driver_id === req.session.userId` or the user with that id is a trip leader.
3. The routes, in `backend/routes/rides.js`:

   ```js
   router.get('/api/rides', listRides);
   router.post('/api/rides', requireAuth, createRide);
   router.post('/api/rides/:id/riders', joinRide);
   router.patch('/api/rides/:id', requireAuth, requireDriverOrLeader, updateRide);
   router.delete('/api/rides/:id', requireAuth, requireDriverOrLeader, cancelRide);
   router.get('/api/me', requireAuth, getMe);
   ```

4. `createRide` and `joinRide` take the user from `req.session.userId`.
5. In React, show the Edit and Cancel buttons only to the ride's driver and to trip leaders, and
   the Join button only to someone signed in.

Would you agree to this as it stands? If not, what would you change?

### whole-plan

Your agent's table for `DEPLOY.md`:

| Action | Not signed in | Signed-in member | Driver of the ride | Trip leader |
| --- | --- | --- | --- | --- |
| See the rides | yes | yes | yes | yes |
| Offer a ride | no | yes | yes | yes |
| Edit a ride | no | no | yes | yes |
| Cancel a ride | no | no | yes | yes |
| Join a ride | no | yes | yes | yes |
| See your own name and picture | no | yes | yes | yes |

And its plan for enforcing it:

1. The `users` table holds `id`, `google_id` (Google's id for the user), `name`, `email`,
   `picture_url` and `role`, which is `'member'` by default. You set `'leader'` by hand for the
   trip leaders.
2. `requireAuth` refuses the request unless `req.session.userId` is set.
3. `requireDriverOrLeader` loads the ride and refuses the request unless
   `ride.driver_id === req.session.userId` or the user with that id is a trip leader.
4. The routes, in `backend/routes/rides.js`:

   ```js
   router.get('/api/rides', listRides);
   router.post('/api/rides', requireAuth, createRide);
   router.patch('/api/rides/:id', requireAuth, requireDriverOrLeader, updateRide);
   router.delete('/api/rides/:id', requireAuth, requireDriverOrLeader, cancelRide);
   router.post('/api/rides/:id/riders', requireAuth, joinRide);
   router.get('/api/me', requireAuth, getMe);
   ```

5. `createRide` and `joinRide` take the user from `req.session.userId`.
6. In React, show the Edit and Cancel buttons only to the ride's driver and to trip leaders, and
   the Join button only to someone signed in.

Would you agree to this as it stands? If not, what would you change?

### confirm-cancel

Your agent reports: "The rules in the table are in place and deployed to Burrowhost."

Take the rule that a member who didn't offer a ride may not cancel it. Which request would you make
to show this rule holds, and what should it get back?

### confirm-join

Your agent reports: "The rules in the table are in place and deployed to Burrowhost. I checked the
sign-in rule myself: in a private window, where I'm not signed in, I clicked Join on Marco's ride
to the gorge, and the site sent me straight to Google's sign-in page."

Take the rule that someone not signed in may not join a ride. Does the agent's check show that this
rule holds? Which request would you make to show this rule holds, and what should it get back?
