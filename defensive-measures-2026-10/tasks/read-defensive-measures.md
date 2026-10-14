# After it's live: four defenses against common problems

Consider a scenario. Swapboard is a small app where students post textbooks they want to trade. It has a page, a
server and a database, all on a host. It recently went live: anyone with the address can use
it. During development, the only visitor was its author. Now the visitors are strangers. Some of them are
programs rather than people. Some are malicious. Several things can protect an app in that
position. Below are a few that an agent working on a live app might bring up that you should be prepared to make decisions about. Or if an agent doesn't bring them up, you might want to.

## Rate limit

A script finds Swapboard's sign-up address and asks it for a new account forty
times a second. Each request is perfectly ordinary; there are just far too many of them, and the
server slows to a crawl for everyone else. A **rate limit** caps how many requests one visitor can
make in a stretch of time, say twenty a minute. Past the cap, the server stops doing the work and
answers with a refusal (status code 429, "Too Many Requests") until the stretch is over. Some hosts
and libraries call this **throttling**.

Don't confuse it with the limits on your hosting plan. An overage is what your host charges when
your app uses more than the plan includes. A rate limit is a cap *your app* puts on *a visitor*.

## Input validation

Swapboard's form for posting a book has a title box that won't accept more than 100 characters. Suppose a bot skips the form entirely and sends the server a request directly. Suppose the "title" is
five megabytes long. The form's check, which would run in the browser using JavaScript, doesn't run because the bot skipped using the form entirely. **Input validation** is the server checking what arrives, before it saves or acts on it, and refusing what isn't what it expected: too long, the wrong kind of thing, a field that should be there and isn't. It's also sometimes called **server-side validation**, to set it apart from the check in the browser's form, which is there to help honest visitors fill it in and which anyone can bypass. Server-side input validation is a good idea to protect your app.

## Alert

Suppose Swapboard's server log has been recording an error every few minutes for two days: a
book page that crashes when its photo is missing. The log has it all. But nobody has read the log. An
**alert** is a message that comes to you, by email or text or chat, when something about the live
app crosses a **threshold** you set, a line you choose ahead of time: more than three errors in an
hour, say, or no answer at all. The
log is the record; the alert is what tells you to go and look at it. A host's health check is a
neighboring idea, but different: it is the host asking your app whether it still answers,
so the host can act. An alert is for you. Setting one up is often called **alerting**.

## Backup

Suppose a code update changes how Swapboard stores its trades. There's a mistake in that code. Every time a trade is recorded, it empties the table of books. Rolling back to the last working deploy brings back the old code, but the books
are gone: a rollback restores code, not data. Git history doesn't help either, because the books
were never in the repository; they were only in the database. A **backup** is a copy of the
app's data, kept apart from it, that can be put back after the data is lost; putting it back is
called **restoring** it. For apps like Swapboard the data is in a database, so you'll often hear the term
**database backup**. Many database hosts make one every day on their own, and call it a
**snapshot**.

## Before and after

Two other defenses come before an app goes live: keeping secrets out of the repository, and
deciding what a visitor who isn't signed in may do. The deploy-config and sign-in-and-permissions
topics cover those. These four are the ones that matter once it's live and strangers are using it.
