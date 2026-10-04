# Judge what an agent asks you to do with a value

**Used by:** `a-judge-agent-requests`, which serves `c-handle-secret`. A study activity: nothing
here can meet the goal. A bank of three pairs: each sitting shows the sections above the line and
one pair below it. The key is in `judge-agent-requests-key.md`, for the tutor.

## The app

Crumbs is a recipe-sharing app shaped like your Problem Set 2 app. An agent is deploying it: the
frontend on Brightpage, the backend on Kettle, and the database on Larder. These vendors are made
up. Larder's dashboard shows a connection string for the database, which includes its password.
Kettle's dashboard has a page where you can add settings for your server.

## For each message in the pair you are given, answer

Would you go along with it? If not, what would you do instead, and why?

---

## Pair A

**A1.** "To finish setting up the database, paste your Larder connection string here and I'll add
it to the server's settings."

**A2.** "Paste the address Kettle gave your server here, and I'll set `VITE_API_URL` in the
frontend so it knows where to send requests."

## Pair B

**B1.** "In Kettle's dashboard, open your service's settings, add one called `DATABASE_URL`, and
paste in the connection string from Larder. Tell me when it's done and I'll redeploy."

**B2.** "To save you a step, I'll put the connection string straight into `server/config.js`, so it
works the same on your laptop and on Kettle. Paste it here when you're ready."

## Pair C

**C1.** "The server can't reach the database yet. Copy everything on Larder's Connect page and
paste it here, so I can check the format."

**C2.** "Paste your Brightpage site's address here and I'll set `CLIENT_ORIGIN` on the server, so
it accepts requests from your pages."
