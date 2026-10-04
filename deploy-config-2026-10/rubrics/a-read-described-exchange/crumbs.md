Brightpage hosts only the frontend, Kettle only the backend, and Larder only the database, so in
this scenario a vendor's name settles which part an address belongs to. What each setting is for
is in the agent's answer; accept any wording that says the same thing. A value is a secret when
someone holding it could get into something of yours; an address the app's users see is not.

### q1

- **goal:** `c-spot-secret`
- **answer:** It is where the React app sends its requests for recipes. It needs the backend's
  address (the one Kettle gave the service), even though the frontend reads it. Not a secret:
  anyone using the app can see where its requests go.
- **credit:** full for "not a secret" with a reason like the address being public; half for "not
  a secret" with no reason.
- **tutor note:** the part is not credited here, because Kettle's name gives it away; but if the
  learner says "the frontend's address", read off the name, ask where the requests actually go.

### q2

- **goal:** `c-spot-secret`
- **answer:** It tells the server which pages may call its API, so other sites can't. It needs the
  frontend's address (the Brightpage site), even though it is set on the backend. Not a secret:
  the site's address is public.
- **credit:** full for "not a secret" with a reason like the address being public; half for "not
  a secret" with no reason.
- **tutor note:** the part is not credited here, because Brightpage's name gives it away; but if
  the learner says "the backend's address", because the backend is where it is set, ask whose
  pages it is letting in.

### q3

- **goal:** `c-spot-secret`
- **answer:** It is how the server reaches the database. It needs the database's connection
  details, copied from Larder. It is a secret: whoever holds it can get into the database.
- **credit:** full for "a secret" because holding it gets someone into the database; half for "a
  secret" with no reason or a reason that wouldn't make it one.

### q4

- **goal:** `c-spot-secret`
- **answer:** It is the port the server listens on. It needs nobody's value: Kettle sets it. Not a
  secret: it lets nobody into anything.
- **credit:** full for "not a secret" with a reason like it unlocking nothing; half for "not a
  secret" with no reason.
- **tutor note:** the near-miss for the part is "the backend's address"; a port is not an address,
  and nothing is entered.

### q5

- **goal:** `c-spot-secret`
- **answer:** The server sends it with every request to the database to prove it is allowed in. It
  is part of the database's connection details. It is a secret: anyone holding it gets in too.
- **credit:** full for "a secret" because holding it gets someone into the database; half for "a
  secret" with no reason.
- **tutor note:** the near-miss is "not a secret, it's just a token", because it isn't an address
  or a password.
