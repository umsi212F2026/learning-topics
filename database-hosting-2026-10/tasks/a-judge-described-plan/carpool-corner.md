Carpool Corner lets students post rides home for school breaks and lets other students ask for a
seat. It has a React frontend and an Express backend. The backend keeps its data in a SQLite file at
`server/data/rides.sqlite`, with two tables, `rides` and `seat_requests`.

Carpool Corner will be deployed to Mossgate, a made-up host. Mossgate's servers have ephemeral
disks, so anything written to them is gone after every redeploy or restart. A volume can be attached
to a service, mounted at `/data`, and only files under `/data` are kept. Mossgate also offers
managed Postgres as a separate service.

### q1

Carpool Corner's coding agent proposes this plan:

> Here's what I'll do to deploy Carpool Corner's database on Mossgate:
>
> 1. Attach a Mossgate volume to the backend service, mounted at `/data`.
> 2. Deploy the backend from your repository, with the environment setting
>    `DATABASE_FILE=/app/server/data/rides.sqlite`.
> 3. When the backend starts, it creates the `rides` and `seat_requests` tables if they don't exist.
> 4. Deploy the frontend and point it at the backend.
>
> With the volume attached, your data will be safe.

Will this plan's data survive a redeploy? Say yes or no, and name the step in the plan that decides
it.

### q2

Carpool Corner's coding agent proposes this plan:

> Carpool Corner deployment plan:
>
> 1. Add a volume to the backend service, mounted at `/data`. Mossgate notes that a service with a
>    volume is down for a few seconds on each redeploy, while the old server lets go of the volume
>    and the new one picks it up.
> 2. Configure the backend to open its SQLite database at `/data/rides.sqlite`.
> 3. Deploy the backend. On startup it makes the `rides` and `seat_requests` tables if they are
>    missing.
> 4. Deploy the frontend.
>
> Your riders' posts will be kept.

Will this plan's data survive a redeploy? Say yes or no, and name the step in the plan that decides
it.

### q3

Carpool Corner's coding agent proposes this plan:

> To get Carpool Corner's data onto Mossgate:
>
> 1. Give the backend service a volume at `/data`, and have the backend read and write its database
>    at `/data/rides.sqlite`.
> 2. Copy `server/data/rides.sqlite` from your laptop to `/data/rides.sqlite`, so production starts
>    with the rides you already have.
> 3. Deploy the backend, which opens that file.
> 4. Deploy the frontend.
>
> Nothing will be lost.

Does production get a database of its own, built by the code rather than copied from the laptop or
shared with development? Say yes or no, and name the step in the plan that decides it.

### q4

Carpool Corner's coding agent proposes this plan:

> Plan for launching Carpool Corner on Mossgate:
>
> 1. Create a Mossgate web service for the Express backend, built from your repository.
> 2. Deploy it. The first time the backend starts, it creates the `rides` and `seat_requests`
>    tables, empty.
> 3. Deploy the React frontend and set it to call the backend's Mossgate address.
>
> You're ready for your first riders.

Does production get a database of its own, built by the code rather than copied from the laptop or
shared with development? Say yes or no, and name the step in the plan that decides it.
