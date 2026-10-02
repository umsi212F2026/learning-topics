# Key: judge-plan-weighings

**For the tutor only.** Used by `a-judge-plan-weighings`. Never show this file to the learner; the learner's copy is `judge-plan-weighings.md`.

Show the learner the task file's header and the one choice being served, and none of this file.
Take the learner's verdict before commenting. Each table row is one bank item; cases: complete
`v1` (chooses S), `v2` (chooses H); unsupported claims `v3`, `v5`, `v8`; misses the extra
vendors and agent access `v4`; a card treated as a requirement `v6`; no case for the other plan
`v7`. The two lists below are what every item is judged against.

### Must name: differences that matter for this app (about twenty users, a class project)

A complete answer names every item in this group. This is the list each choice is checked
against; `v1` and `v2` name all of it.

- **Sleep:** Harbor's server sleeps after 15 minutes idle and the next visitor waits about a
  minute; Kettle's never sleeps.
- **Past a limit:** Harbor's free database expires after 30 days and is deleted after 14 more
  unless paid for, which for a project running more than six weeks is the largest difference in
  the terms.
- **Card:** none of the four requires one. Having one on file turns a pause into a bill on Harbor
  (bandwidth) and on Kettle (credit); Brightpage and Ledger can't bill on their free plans. Saying
  "I'd keep no card on the ones that can bill" covers the second half.
- **Agent access:** Harbor gives one tool reaching all three parts; Plan S needs three, so three
  sets of credentials for the agent.
- **Moving:** easy from both: ordinary Node, plain files, `pg_dump`.
- **What the extra vendors add:** three accounts; secrets and settings to copy between them
  (Ledger's connection string into Kettle, Kettle's address into the frontend's build) and
  credentials for the agent on each; three dashboards and log places when something breaks.

### Present in the terms, but not deciding for this app

An answer may name these and should not be marked down for leaving them out. Leaning on one as a
main reason is fine only if what it says matches the terms.

- Harbor's 750-hour limit: one web service running all month uses about 730 hours, so it isn't
  reached.
- Kettle stopping when its $1 credit runs out: the terms say the credit keeps a small server
  running all month.
- Brightpage's 100 GB cap and Harbor's 100 GB bandwidth line: twenty users won't come near them
  (they matter only with a card on file, which the card item already covers).
- Ledger's database pausing after 5 minutes: it wakes in under a second.
- Ledger refusing writes past 0.5 GB: a class project won't reach it.
- Brightpage having no request logs: it runs no code, so there is nothing to log.
- Ledger's agent tool being able to change or delete data: a real caution about agent access, not
  a difference between the plans' terms that decides the choice. Worth raising in discussion.
- Kettle's `kettle.toml`: a small extra when moving.

| choice | verdict | what decides it |
| ------ | ------- | --------------- |
| v1 | complete | Names every must-name difference, the cost of the extra vendors, nothing unsupported, and a real case for H. It also names several of the not-deciding items (Kettle's credit, Ledger's pause, Brightpage's logs), correctly. |
| v2 | complete | Names every must-name difference, and chooses the other plan with equal care. It leaves out Kettle's credit stop and Brightpage's pause, which are in the not-deciding group. Its case for S is strong and specific. Put v1 and v2 side by side: opposite choices, both meeting the criterion, which is why the choice itself is not part of it. |
| v3 | fails on three counts (for the unsupported claims, "nothing in the terms says this" is enough) | "Free forever" and "never charges" are not supported: the database expires, and a card would allow billing. Names almost no differences. No case for S. |
| v4 | misses the cost of the extra vendors, and agent access | Its differences are right, but it never says what three vendors add beyond "one account" in the case for H, and says nothing about what the agent can reach. A thin case for the other plan. |
| v5 | names things the terms don't support ("nothing in the terms says this" is enough) | Faster, more reliable and more secure appear nowhere in the terms. The rest is thin: no card, no moving, no secrets, and a one-word case for H. |
| v6 | names something the terms don't support, and misses the card risk | Kettle does not need a card; the terms say the opposite. Treats a card as a requirement rather than a risk, so never says what having one would cost on Harbor. Misses moving. |
| v7 | no case for the other plan | Close to complete on the differences and the extra vendors, then dismisses H instead of stating its strongest case. |
| v8 | names things the terms don't support ("nothing in the terms says this" is enough) | Keeping the server awake by pinging it and making a new database each month are plans the terms say nothing about (and the second loses the data each time). Look at whether it names the differences before the workarounds: it does name sleep, expiry, agent access and the extra vendors, but not the card requirement or moving. |

Pairs for the tutor's question "how does this one differ from the one you did before?": v1 and
v2 (opposite choices, both complete, which is why the choice itself is not judged); v6 and v2
("needs a card" against "a card on file lets them bill you", the distinction this goal most often
blurs); v7 and v1 (nearly the same differences, but no case for the other plan). Ask it only when
the partner has already been served.
