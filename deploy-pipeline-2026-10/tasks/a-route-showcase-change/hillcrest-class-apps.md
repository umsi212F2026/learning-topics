Answer each question in two or three sentences.

Your GitHub username is `sam-tinkers`, and your app lives in your repository
`sam-tinkers/habit-hop`. Your web development class at Hillcrest keeps a list of everyone's apps
in the repository `hillcrest-webdev/class-apps`, which belongs to the class's GitHub account. You
can read it, but you can't push to it.

The class list lives in one file, `apps.json`, with an entry per app giving its `name`, `student`,
`url` and `blurb`. Your change is to add an entry for Habit Hop to that list. A check called
`verify-apps` runs on every pull request to the class list and fails if an entry is missing a
field or is badly formed.

Your agent will do the typing. Your job is to say what should happen.

### q1

Your agent proposes: "I'll make a branch called `add-habit-hop` in `hillcrest-webdev/class-apps`,
add your entry to `apps.json` there, and push the branch." Would you go along with this? If not,
where should it go?

### q2

Your change is pushed, on a branch called `add-habit-hop` in `sam-tinkers/class-apps`, your own
copy of the class list. Your agent reports: "I've opened a pull request from
`sam-tinkers/class-apps:add-habit-hop` into `hillcrest-webdev/class-apps:main`." Is that right? If
not, what should it be?

### q3

Your pull request, from `sam-tinkers/class-apps` branch `add-habit-hop` into
`hillcrest-webdev/class-apps` branch `main`, is open, and its check has failed with this message:

```
verify-apps: apps.json: entry "Habit Hop" has unknown field "studnet" and is missing required field "student"
```

What do you do?
