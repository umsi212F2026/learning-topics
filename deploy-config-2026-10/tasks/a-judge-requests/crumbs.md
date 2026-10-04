Crumbs is a recipe-sharing app shaped like your Problem Set 2 app. An agent is deploying it: the
frontend on Brightpage, the backend on Kettle, and the database on Larder. These vendors are made
up. Larder's dashboard shows a connection string for the database on its Connect page, and the
string includes the database's password.
Kettle's dashboard has a page where you can add settings for your server.

Each question is one message from the agent. Say whether you would go along with it.

### q1

**Agent:** To finish setting up the database, paste your Larder connection string here and I'll add it to
the server's settings.

Would you go along with this?

### q2

**Agent:** Paste the address Kettle gave your server here, and I'll set `VITE_API_URL` in the frontend so
it knows where to send requests.

Would you go along with this?

### q3

**Agent:** In Kettle's dashboard, open your service's settings, add one called `DATABASE_URL`, and paste in
the connection string from Larder. Tell me when it's done and I'll redeploy.

Would you go along with this?

### q4

**Agent:** To save you a step, I'll put the connection string straight into `server/config.js`, so it works
the same on your laptop and on Kettle. Paste it here when you're ready.

Would you go along with this?

### q5

**Agent:** The server can't reach the database yet. Copy everything on Larder's Connect page and paste it
here, so I can check the format.

Would you go along with this?

### q6

**Agent:** Paste your Brightpage site's address here and I'll set `CLIENT_ORIGIN` on the server, so it
accepts requests from your pages.

Would you go along with this?
