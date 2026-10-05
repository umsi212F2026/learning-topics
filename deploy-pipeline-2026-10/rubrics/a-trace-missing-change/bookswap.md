Shape `red-check` (Easy). The commit with the new button text is on `main` on GitHub, but the
workflow's tests failed on it, so the workflow never reached its Pinecart deploy step and Ropewalk
skipped the commit. Both hosts are still serving the commit before it. The Saturday setting is a
true red herring: both later Pinecart deploys were built after it was saved.

Evidence, to be read word for word, one place at a time, only the one asked for.

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
a41c9e2 (HEAD -> main, origin/main) Change sign-up button text to Join the swap
7d03b18 Show each book's condition on its listing
e95f6a0 Add search by course number
```

**GitHub**

- Latest commits on `main`: `a41c9e2` Change sign-up button text to Join the swap (today 2:10
  pm); `7d03b18` Show each book's condition on its listing (today 10:35 am); `e95f6a0` Add search
  by course number (yesterday 4:08 pm).
- Open pull requests: none.
- Checks on `a41c9e2`: workflow `test-and-deploy`, failed. Step "Run frontend tests" failed:
  `SignupButton.test.jsx: expected button text "Sign up", received "Join the swap"`. Step "Run
  backend tests" passed. Step "Deploy frontend to Pinecart" skipped.
- Checks on `7d03b18` and `e95f6a0`: workflow `test-and-deploy`, passed.

**Pinecart's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `7d03b18` | today 10:39 am | Live |
| `e95f6a0` | yesterday 4:12 pm | Replaced |
| `c52d0f4` | Friday 1:47 pm | Replaced |

Shown with it, Pinecart's Settings page:

- `VITE_API_URL` = `https://bookswap-api-2.ropewalk.example`, last saved Saturday 11:20 am.
- Clear CDN cache on deploy: on.

**Ropewalk's deploy list**

| commit | time | status |
| ------ | ---- | ------ |
| `a41c9e2` | today 2:13 pm | Skipped (checks failed) |
| `7d03b18` | today 10:38 am | Live |
| `e95f6a0` | yesterday 4:11 pm | Replaced |

**The page in the browser**

- Normal load: the button says "Sign up".
- Reload that skips the browser's cache: "Sign up".
- Private window, or another device: "Sign up".
- The URL with `?v=2` added: "Sign up".

### q1

- **goal:** `c-find-missing-change`
- **cases:** tests-failed
- **answer:** The commit reached `main`, but its tests failed: the frontend test still expects
  "Sign up". So the workflow never ran Pinecart's deploy command for it, and Ropewalk skipped it
  for its failed check, and the live site is still `7d03b18`. Next: make the tests pass (update
  `SignupButton.test.jsx` to expect "Join the swap", running the tests locally) and push the fix
  to `main`, which deploys both parts once the checks pass.
- **credit:** full for the reason (the tests failed on the commit, so it was never deployed) and
  the next step (make the tests pass and push). Half for that reason with the next step missing or
  wrong, such as pressing Pinecart's Rebuild, re-running the failed workflow unchanged, or turning
  "Wait for GitHub checks" off. None for any other reason, such as the browser's or the CDN's copy,
  a failed deploy, or the Saturday setting.
- **tutor note:** if they propose Rebuild, ask which commit Rebuild builds: the latest deploy's,
  `7d03b18`, which doesn't have the new text. If they settle on the Saturday setting, ask when it
  was saved against the time of the Live Pinecart deploy.
