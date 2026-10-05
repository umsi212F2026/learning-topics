Your classmate Priya has the GitHub username `priya-builds`. Her app is in the repository
`priya-builds/trail-log`. The Lakeside Coders club keeps a showcase of members' apps in the
repository `lakeside-coders/demo-day`, which Priya can read but can't push to. The showcase holds
one file per app in its `projects/` folder, and a check called `check-entry` runs on every pull
request to it. Priya wanted to add an entry for `trail-log` to the showcase, and had her agent do
the typing.

Each question below is a separate account of how that went, told by Priya or summarised by her
agent. Judge each one on its own. For each, answer: would you have gone along with this? If a step
goes wrong, which one, and what should have happened instead? Answer in two or three sentences.

### q1

Priya's account:

1. I read the showcase's README to see what an entry looks like.
2. I asked my agent to write an entry for `trail-log` in that format.
3. It added `projects/trail-log.md` to my `priya-builds/trail-log` repository on a new branch,
   `demo-day-entry`, and pushed that branch.
4. It opened a pull request from `demo-day-entry` into `main` of `priya-builds/trail-log`.

### q2

The agent's summary:

1. Forked `lakeside-coders/demo-day` into Priya's account, as `priya-builds/demo-day`.
2. Created a branch `add-trail-log` in the fork and added `projects/trail-log.md` on it.
3. Pushed `add-trail-log` to `priya-builds/demo-day`.
4. Opened a pull request with base repository `priya-builds/demo-day`, base branch
   `add-trail-log`, and head repository `lakeside-coders/demo-day`, compare branch `main`.

### q3

Priya's account:

1. I had my agent fork the showcase into my account, as `priya-builds/demo-day`.
2. It made a branch `trail-log-entry` in my fork, added `projects/trail-log.md`, and pushed the
   branch.
3. It opened a pull request from `priya-builds/demo-day`, branch `trail-log-entry`, into
   `lakeside-coders/demo-day`, branch `main`.
4. `check-entry` failed with the message `projects/trail-log.md: missing field "url"`.
5. My agent added the `url` field on a new branch, `trail-log-entry-fix`, pushed that branch to my
   fork, and opened a second pull request from it into the showcase's `main`.

### q4

The agent's summary:

1. Forked `lakeside-coders/demo-day` into Priya's account, as `priya-builds/demo-day`.
2. Created a branch `add-trail-log` in the fork and added `projects/trail-log.md` on it.
3. Pushed `add-trail-log` to `priya-builds/demo-day`.
4. Opened a pull request with base repository `lakeside-coders/demo-day`, base branch `main`, and
   head repository `priya-builds/demo-day`, compare branch `add-trail-log`.
5. `check-entry` failed because the entry had no `url` field. Added the field on `add-trail-log`
   and pushed it to `priya-builds/demo-day`.
6. The pull request picked up the new commit, `check-entry` ran again, and it passed.
