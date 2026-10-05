Answer each question in two or three sentences.

Your classmate Priya's GitHub username is `priya-builds`, and her app lives in her repository
`priya-builds/plant-pal`. The Eastgate coding club keeps a wall of its members' apps in the
repository `eastgate-coders/app-wall`, which belongs to the club's GitHub account. Priya can read
it, but she can't push to it.

The app wall keeps its list in one file, `apps.json`, with an entry per app giving its `name`,
`author` and `url`. Priya's change is to add an entry for Plant Pal. A check called
`check-app-wall` runs on every pull request to the app wall and fails if an entry is missing a
field or is badly formed. Her agent did the typing.

Each question below is a separate account of how Priya got her entry onto the app wall. Read each
one on its own.

### q1

Priya tells it like this:

1. I opened `eastgate-coders/app-wall` on GitHub and read `apps.json` to see how the entries
   look.
2. I asked my agent to add an entry for Plant Pal.
3. The agent added the entry to an `apps.json` file in my own repository,
   `priya-builds/plant-pal`, on a new branch called `add-plant-pal`, and pushed that branch to
   `priya-builds/plant-pal`.
4. It opened a pull request in `priya-builds/plant-pal`, from `add-plant-pal` into `main`.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q2

Priya's agent summed up what it did like this:

1. I forked `eastgate-coders/app-wall` into your account, as `priya-builds/app-wall`.
2. I cloned your fork, made a branch called `add-plant-pal`, and added your entry to `apps.json`.
3. I pushed `add-plant-pal` to `priya-builds/app-wall`.
4. I opened a pull request from `eastgate-coders/app-wall` branch `main` into
   `priya-builds/app-wall` branch `add-plant-pal`.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q3

Priya tells it like this:

1. My agent forked `eastgate-coders/app-wall` into my account, as `priya-builds/app-wall`.
2. It added my entry to `apps.json` on a branch called `add-plant-pal` in my fork, and pushed the
   branch there.
3. It opened a pull request from `priya-builds/app-wall` branch `add-plant-pal` into
   `eastgate-coders/app-wall` branch `main`.
4. `check-app-wall` failed on the pull request with this message:
   `apps.json: entry "Plant Pal" is missing required field "url"`.
5. The agent made a new branch called `add-plant-pal-fixed` in my fork, added the `url` there,
   pushed it, and opened a second pull request from `add-plant-pal-fixed` into
   `eastgate-coders/app-wall` branch `main`.
6. `check-app-wall` passed on the second pull request.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q4

Priya's agent summed up what it did like this:

1. I forked `eastgate-coders/app-wall` into your account, as `priya-builds/app-wall`.
2. I made a branch called `add-plant-pal` in your fork, added your entry to `apps.json`, and
   pushed the branch to `priya-builds/app-wall`.
3. I opened a pull request from `priya-builds/app-wall` branch `add-plant-pal` into
   `eastgate-coders/app-wall` branch `main`.
4. `check-app-wall` failed on the pull request with this message:
   `apps.json: entry "Plant Pal" is missing required field "url"`.
5. I checked out the same branch, `add-plant-pal` in `priya-builds/app-wall`, added the `url` to
   your entry, committed, and pushed to that branch. I didn't open another pull request: the open
   one picked up the new commit.
6. `check-app-wall` ran again on the same pull request and passed.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?
