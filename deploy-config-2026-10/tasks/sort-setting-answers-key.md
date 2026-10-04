# Key: sort what an agent says about six settings

**For the tutor only.** Never show this file to the learner. It goes with
`sort-setting-answers.md`.

| # | setting | whose value | secret | what decides it |
| - | ------- | ----------- | ------ | --------------- |
| 1 | `FRONTEND_API_URL` | the backend's address | no | The name says "frontend" because the frontend uses it, but what it holds is where the requests go: the backend. The near-miss is sorting by the name. |
| 2 | `CLIENT_ORIGIN` | the frontend's address | no | Set on the backend, but it holds the address of the pages allowed to call it, which is the frontend's. The near-miss is "backend", because the backend is where it lives. |
| 3 | `PG_CONNECTION` | the database's connection details | yes | A connection string from Larder includes the database's password. |
| 4 | `PORT` | nobody's: Kettle sets it | no | Nothing to copy. The near-miss is "the backend's address"; a port is not an address, and the student enters nothing. |
| 5 | `API_BASE` | the backend's address | no | "Your Harbor address" is ambiguous, because Harbor gives the static site and the web service an address each. The requests go to the backend, so it is the web service's address. The near-miss is copying the first Harbor address in sight, often the site's. |
| 6 | `LARDER_TOKEN` | the database's connection details | yes | Not an address at all, but it is what lets the server into the database. Anyone holding it gets in too. The near-miss is "not a secret, it's just a token". |

**What each is for.** It is in the agent's answer in the task file. Accept any wording that says
the same thing.

**The rule.** A good rule says something like: sort by what the value is (whose address, or what
it unlocks), not by which part reads the setting or what its name suggests; and a value is a
secret when holding it lets you into something. A rule that sorts by the setting's name, or by
where the setting is entered, should be pushed on with items 1 and 2. A rule that looks up which
vendor the answer names works for items 1 to 4 but not for item 5, where Harbor hosts two parts;
push on it there.
