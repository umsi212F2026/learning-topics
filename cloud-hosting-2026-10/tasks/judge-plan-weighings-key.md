# Key: judge-plan-weighings

**For the tutor only.** Used by `a-judge-plan-weighings`. Never show this file to the learner; the learner's copy is `judge-plan-weighings.md`.

Show the learner the task file's header and the one choice being served, and none of this file.
Take the learner's verdict before commenting. Each table row is one bank item; cases: complete
`v1` (chooses H), `v2` (chooses S); unsupported claims `v3`, `v5`; misses the extra
vendor's cost and agent access `v4`; a card treated as a requirement `v6`; no case for the other
plan `v7`; a supported workaround that still misses the card and moving `v8`. The two lists
below are what every item is judged against, and the verdict column lists every miss.

### Must name: differences that matter for this app (about twenty users, a class project)

A complete answer names every item in this group. This is the list each choice is checked
against; `v1` and `v2` name all of it.

- **Sleep:** Harbor's server sleeps after 15 minutes idle and the next visitor waits about a
  minute; Kettle's never sleeps.
- **Past a limit:** Kettle's credit lasts about three weeks, so its server stops in the last week
  of the month, which is grading week, unless a card is on file, and then it bills. Harbor's
  server doesn't stop.
- **Card:** none of the three requires one. Having one on file turns a stop or a pause into a bill
  on Harbor (bandwidth) and on Kettle (credit); Brightpage can't bill on its free plan. Saying
  "I'd keep no card on the ones that can bill" covers the second half.
- **Agent access:** Harbor gives one tool reaching both parts; Plan S needs two, so two sets of
  credentials for the agent.
- **Moving:** easy from both: ordinary npm and Node, plain files.
- **What the extra vendor adds:** a second account; Kettle's address copied into the frontend's
  build, and credentials for the agent on each; two dashboards and log places when something
  breaks.

### Present in the terms, but not deciding for this app

An answer may name these and should not be marked down for leaving them out. Leaning on one as a
main reason is fine only if what it says matches the terms.

- Harbor's 750-hour limit: one web service running all month uses about 730 hours, so it isn't
  reached.
- Brightpage's 100 GB cap and Harbor's 100 GB bandwidth line: twenty users won't come near them
  (they matter only with a card on file, which the card item already covers).
- Brightpage having no request logs: it runs no code, so there is nothing to log.
- Kettle's `kettle.toml`: a small extra when moving.

| choice | verdict | what decides it |
| ------ | ------- | --------------- |
| v1 | complete | Names every must-name difference, the cost of the extra vendor, nothing unsupported, and a real case for S. It also names two not-deciding items (Brightpage's logs, Kettle's config), correctly. |
| v2 | complete | Names every must-name difference, and chooses the other plan with equal care. Its case for H is strong and specific. Put v1 and v2 side by side: opposite choices, both meeting the criterion, which is why the choice itself is not part of it. |
| v3 | names things the terms don't support; misses sleep, Kettle's stop, the card, agent access, moving, and the extra vendor's secrets and log places; no case for S | "Free forever" and "never charges" are not supported: a card on file would let Harbor bill ("nothing in the terms says this" is enough). It names only the second account. |
| v4 | misses whether a card is required, agent access, and what the extra vendor adds beyond one account | Its differences are right as far as they go, but the case for H is one account and nothing more, and it says nothing about what the agent can reach. |
| v5 | names things the terms don't support; misses Kettle's stop, the card, moving and the address copied into the build | Faster, more reliable and more secure appear nowhere in the terms ("nothing in the terms says this" is enough). Its two logins and two places to look do count as what the extra vendor adds. A one-word case for H. |
| v6 | names something the terms don't support; misses the card risk, Kettle's stop and moving | No vendor needs a card to sign up; the terms say so in their first line. Treating a card as a requirement, it never says what having one would cost on Harbor or Kettle. Its agent sentence is right: Harbor's one tool deploys, reads logs and sets environment variables for both parts (it can't delete services or change plans, which doesn't matter here). |
| v7 | no case for the other plan; misses whether a card is required | Close to complete on the differences and the extra vendor, then dismisses S instead of stating its strongest case. |
| v8 | misses the card and moving | Pinging every ten minutes would keep Harbor's server awake within the terms (about 744 hours a month, under the 750), so the workaround is supported, and worth saying so. It names sleep, Kettle's stop, agent access and the extra vendor, but not the card or moving. |

Pairs for the tutor's question "how does this one differ from the one you did before?": v1 and
v2 (opposite choices, both complete, which is why the choice itself is not judged); v6 and v1
(both choose H; "needs a card" against "a card on file lets them bill you", the distinction this goal most often
blurs); v7 and v1 (both choose H with nearly the same differences, but v7 has no case for the other plan). Ask it only when
the partner has already been served.
