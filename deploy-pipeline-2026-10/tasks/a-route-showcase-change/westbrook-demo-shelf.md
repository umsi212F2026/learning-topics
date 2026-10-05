Answer each question in two or three sentences.

Your GitHub username is `kofi-builds`, and your app lives in your repository
`kofi-builds/bus-times`. The Westbrook student developers group keeps a showcase of its members'
apps in the repository `westbrook-devs/demo-shelf`, which belongs to the group's GitHub account.
You can read it, but you can't push to it.

The demo shelf holds one file per app in its `apps/` folder, such as `apps/quiz-quest.json`. Each
file gives the app's `title`, `creator`, `link` and `summary`. Your change is to add
`apps/bus-times.json`, an entry for your app. A check called `entry-check` runs on every pull
request to the demo shelf and fails if an entry is missing a field or is badly formed.

Your agent will do the typing. Your job is to say what should happen.

### q1

Your agent proposes: "I'll fork `westbrook-devs/demo-shelf` into your account, add your entry on
a new branch there, and push that branch to your fork." Would you go along with this? If not,
where should it go?

### q2

Your change is pushed, on a branch called `add-bus-times` in `kofi-builds/demo-shelf`, your own
copy of the demo shelf. Your agent reports: "I've opened a pull request from
`westbrook-devs/demo-shelf:main` into `kofi-builds/demo-shelf:add-bus-times`." Is that right? If
not, what should it be?

### q3

Your pull request, from `kofi-builds/demo-shelf` branch `add-bus-times` into
`westbrook-devs/demo-shelf` branch `main`, is open, and its check has failed with this message:

```
entry-check: apps/bus-times.json is not valid JSON: unexpected end of input at line 6
```

Your agent proposes: "I'll fix the entry on the same branch, `add-bus-times` in your fork, and
push." Would you go along with this? If not, what should happen instead?
