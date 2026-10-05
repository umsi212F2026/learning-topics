Answer each question in two or three sentences.

Your GitHub username is `mara-codes`, and your app lives in your repository
`mara-codes/study-buddy`. Your class at Northfield keeps a showcase of everyone's apps in the
repository `northfield-cs/showcase`, which belongs to the class's GitHub account. You can read
it, but you can't push to it.

The showcase holds one file per app in its `apps/` folder, such as `apps/flashcard-fox.json`.
Each file gives the app's `name`, `author`, `url` and `description`. Your change is to add
`apps/study-buddy.json`, an entry for your app. A check called `validate-entries` runs on every
pull request to the showcase and fails if an entry is missing a field or is badly formed.

Your agent will do the typing. Your job is to say what should happen.

### q1

Before any pull request exists, where does your change get made and pushed?

### q2

Your change is pushed, on a branch called `add-study-buddy` in `mara-codes/showcase`, your own
copy of the showcase. GitHub's page for opening a pull request asks for a base repository and
branch and a head repository and branch. What do you choose for each?

### q3

Your pull request, from `mara-codes/showcase` branch `add-study-buddy` into
`northfield-cs/showcase` branch `main`, is open, and its check has failed with this message:

```
validate-entries: apps/study-buddy.json is missing required field "url"
```

What do you do?
