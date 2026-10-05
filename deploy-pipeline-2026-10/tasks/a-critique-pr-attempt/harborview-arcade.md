Answer each question in two or three sentences.

Your classmate Tomas's GitHub username is `tomas-ships`, and his app lives in his repository
`tomas-ships/bus-buddy`. The Harborview Makers club keeps an arcade of its members' projects in
the repository `harborview-makers/arcade`, which belongs to the club's GitHub account. Tomas can
read it, but he can't push to it.

The arcade keeps its list in one file, `projects.yaml`, with an entry per project giving its
`title`, `maker` and `link`. Tomas's change is to add an entry for Bus Buddy. A check called
`lint-arcade` runs on every pull request to the arcade and fails if an entry is missing a field or
is badly formed. His agent did the typing.

Each question below is a separate account of how Tomas got his entry into the arcade. Read each
one on its own.

### q1

Tomas tells it like this:

1. I opened `harborview-makers/arcade` on GitHub and read `projects.yaml` to see how the entries
   are laid out. I don't have push access to the arcade.
2. I asked my agent to add an entry for Bus Buddy.
3. The agent created a new repository in my account, `tomas-ships/arcade-entry`, added a
   `projects.yaml` holding my entry, and pushed it to `main` in `tomas-ships/arcade-entry`.
4. It opened a pull request from `tomas-ships/arcade-entry` branch `main` into
   `harborview-makers/arcade` branch `main`.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q2

Tomas's agent summed up what it did like this:

1. I forked `harborview-makers/arcade` into your account, as `tomas-ships/arcade`.
2. I cloned your fork, made a branch called `bus-buddy-entry`, added your entry to
   `projects.yaml`, and committed.
3. I pushed `bus-buddy-entry` to `tomas-ships/arcade`.
4. On GitHub's page for a new pull request, I set the base repository to `tomas-ships/arcade`
   with base branch `bus-buddy-entry`, and the head repository to `harborview-makers/arcade` with
   compare branch `main`, and opened it.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q3

Tomas tells it like this:

1. My agent forked `harborview-makers/arcade` into my account, which made my own copy,
   `tomas-ships/arcade`. I can push to that one.
2. It cloned `tomas-ships/arcade` to my laptop, made a branch called `bus-buddy-entry`, and added
   my entry to `projects.yaml` on that branch.
3. Before pushing, it checked that the clone's `origin` was `tomas-ships/arcade`. Then it pushed
   `bus-buddy-entry` to `origin`, so the branch now sits in `tomas-ships/arcade`.
4. It opened a pull request from `tomas-ships/arcade` branch `bus-buddy-entry` into
   `harborview-makers/arcade` branch `main`.
5. `lint-arcade` failed on the pull request with this message:
   `projects.yaml: entry "Bus Buddy" is missing required field "link"`.
6. The agent added the `link` on `bus-buddy-entry`, committed, and pushed to that branch in
   `tomas-ships/arcade`. The open pull request picked up the new commit.
7. `lint-arcade` ran again on the same pull request and passed.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?
