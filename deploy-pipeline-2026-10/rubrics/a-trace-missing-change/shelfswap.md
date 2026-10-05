Shape `red-check`: the commit is on `main` on GitHub, its check failed, so the workflow never ran
Pinecart's deploy command and Ropewalk skipped the commit. The live app is still the build of the
commit before it. The test that failed is the frontend's own test of the button, which still
expects the old label.

The evidence for each place follows. Read the one asked for, word for word, and only that one.

**git's output on the learner's machine**

`git status`:

```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

`git branch --show-current`:

```
main
```

`git log --oneline -3`:

```
a41c9e2 (HEAD -> main, origin/main) Change post button label to List a textbook
7d03b18 Show the seller's campus on each listing
2f6e5a0 Add search by course code
```

**GitHub: the commits on `main`, pull requests, and checks**

The latest commits on `main`, newest first, with the mark GitHub shows beside each:

```
a41c9e2  Change post button label to List a textbook    red cross    Oct 6, 3:41 pm
7d03b18  Show the seller's campus on each listing       green check  Oct 5, 11:08 am
2f6e5a0  Add search by course code                      green check  Oct 2, 4:01 pm
```

Open pull requests: none.

The checks on `a41c9e2`: one check, the workflow `test-and-deploy`, failed.

```
test-and-deploy   Failed
  Run npm test in client/        failed
      1 failed, 23 passed
      PostButton > shows the post label
        expected "Post a book", received "List a textbook"
  Run npm test in server/        passed (31 passed)
  Deploy frontend to Pinecart    skipped
```

**Pinecart's deploy list**, newest first, with the site's Settings page beside it:

```
7d03b18  Oct 5, 11:12 am  Live
2f6e5a0  Oct 2, 4:05 pm   Failed
```

Settings page:

```
VITE_API_URL    the backend's address on Ropewalk    last saved Sep 28, 2:10 pm
```

The Failed deploy of `2f6e5a0` is a true red herring: its deploy failed, the build of the commit
before it stayed live, and the next deploy, `7d03b18`, went Live. It has nothing to do with the
button.

**Ropewalk's deploy list**, newest first:

```
a41c9e2  Oct 6, 3:41 pm   Skipped (checks failed)
7d03b18  Oct 5, 11:09 am  Live
```

**The page in the browser**, the live app's home page:

- A normal load: the button says "Post a book".
- A reload that skips the browser's cache: the button says "Post a book".
- A private window, or another device: the button says "Post a book".
- The address with `?v=2` added: the button says "Post a book".

### q1

- **goal:** `c-find-missing-change`
- **cases:** tests-failed
- **answer:** The commit reached `main` on GitHub, but its tests failed (the frontend's test of the
  button still expects "Post a book"), so the workflow never ran Pinecart's deploy command and
  Ropewalk skipped the commit; the live app is still the build of `7d03b18`. Next: make the tests
  pass, here by updating the test to expect "List a textbook" (running `npm test` in `client/`
  first), then commit and push, so the new commit's check passes and it deploys.
- **credit:** full for saying the tests failed so the change was never deployed, and that the next
  step is to make the tests pass and push again. Half for the right reason with the next step
  missing or wrong (pressing Pinecart's Rebuild, clearing a cache, sending a request to a deploy
  hook, or pushing again with nothing changed). None for a wrong reason, such as a failed deploy, a
  cache, or a change that never left the machine. Finding out why the test failed is not asked
  for, and an answer that skips it loses nothing. The order of places chosen is recorded, not
  credited.
- **tutor note:** Pinecart's Failed deploy of `2f6e5a0` is the trap. A learner who stops there and
  says the deploy failed has the wrong reason; ask which commit that deploy was. Pressing Rebuild
  is a wrong next step because it builds `7d03b18`, the commit of the latest deploy, again.
