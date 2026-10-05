Answer each question in two or three sentences, or by choosing one option where options are given.

Your GitHub username is `theo-makes`, and your app lives in your repository
`theo-makes/recipe-box`. The Riverside hack club keeps a gallery of its members' apps in the
repository `riverside-hack-club/gallery`, which belongs to the club's GitHub account. You can read
it, but you can't push to it.

The gallery keeps its list in one file, `apps.json`, with an entry per app giving its `name`,
`maker` and `link`. Your change is to add an entry for Recipe Box to that list. A check called
`lint-gallery` runs on every pull request to the gallery and fails if an entry is missing a field
or is badly formed.

Your agent will do the typing. Your job is to say what should happen.

### q1

Your agent proposes: "I'll add your entry to an `apps.json` file in `theo-makes/recipe-box` and
push it to `main`." Would you go along with this? If not, where should it go?

### q2

Your change is pushed, on a branch called `add-recipe-box` in `theo-makes/gallery`, your own copy
of the gallery. GitHub's page for opening a pull request asks for a base repository and branch and
a head repository and branch. Which do you choose?

1. Base `theo-makes/gallery` branch `add-recipe-box`; head `riverside-hack-club/gallery` branch
   `main`.
2. Base `riverside-hack-club/gallery` branch `main`; head `theo-makes/gallery` branch
   `add-recipe-box`.
3. Base `riverside-hack-club/gallery` branch `main`; head `theo-makes/recipe-box` branch
   `add-recipe-box`.
4. Base `theo-makes/gallery` branch `main`; head `theo-makes/gallery` branch `add-recipe-box`.

### q3

Your pull request, from `theo-makes/gallery` branch `add-recipe-box` into
`riverside-hack-club/gallery` branch `main`, is open, and its check has failed with this message:

```
lint-gallery: apps.json: entry "Recipe Box": "link" must start with https://
```

Your agent proposes: "I'll close this pull request and open a fresh one with the fix." Would you
go along with this? If not, what should happen instead?
