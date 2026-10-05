Answer each question in two or three sentences.

Your classmate June's GitHub username is `june-makes`, and her app lives in her repository
`june-makes/recipe-roulette`. Cedar Hall's computing class lists the apps it will show at demo
day in the repository `cedar-hall-cs/demo-day`, which belongs to the class's GitHub account. June
can read it, but she can't push to it.

The demo day list holds one file per app in its `entries/` folder, such as
`entries/quiz-quokka.json`. Each file gives the app's `name`, `team`, `url` and `blurb`. June's
change is to add `entries/recipe-roulette.json`, an entry for her app. A check called
`check-entries` runs on every pull request to the demo day list and fails if an entry is missing a
field or is badly formed. Her agent did the typing.

Each question below is a separate account of how June got her entry onto the demo day list. Read
each one on its own.

### q1

June's agent summed up what it did like this:

1. You told me you don't have push access to `cedar-hall-cs/demo-day`.
2. I read the `entries/` folder in `cedar-hall-cs/demo-day` to see how an entry is laid out.
3. I created a new repository in your account, `june-makes/demo-day-entry`, added
   `entries/recipe-roulette.json` to it, and pushed it to `main` there.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q2

June tells it like this:

1. My agent forked `cedar-hall-cs/demo-day` into my account, as `june-makes/demo-day`.
2. It made a branch called `add-recipe-roulette` in my fork, added `entries/recipe-roulette.json`,
   and pushed the branch to `june-makes/demo-day`.
3. It opened a pull request from `june-makes/demo-day` branch `add-recipe-roulette` into
   `cedar-hall-cs/demo-day` branch `main`.
4. `check-entries` failed on the pull request with this message:
   `entries/recipe-roulette.json: missing required field "url"`.
5. The agent switched to `main` in my fork, wrote `entries/recipe-roulette.json` with the `url`
   included, committed, and pushed `main` to `june-makes/demo-day`. It didn't open another pull
   request.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?

### q3

June's agent summed up what it did like this:

1. I forked `cedar-hall-cs/demo-day` into your account, as `june-makes/demo-day`.
2. I made a branch called `add-recipe-roulette` in your fork, added
   `entries/recipe-roulette.json`, and pushed the branch to `june-makes/demo-day`.
3. On GitHub's page for a new pull request, I set the base repository to
   `cedar-hall-cs/demo-day` with base branch `main`, and the head repository to
   `june-makes/demo-day` with compare branch `add-recipe-roulette`, and opened it. It asks to merge
   your branch into the demo day list's `main`.
4. `check-entries` failed on the pull request with this message:
   `entries/recipe-roulette.json: missing required field "url"`.
5. I added the `url` on `add-recipe-roulette`, committed, and pushed to that branch in
   `june-makes/demo-day`. The open pull request picked up the new commit.
6. `check-entries` ran again on the same pull request and passed.

Would you have gone along with this? If a step goes wrong, which one, and what should have
happened instead?
