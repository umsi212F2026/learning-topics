# After it's live: four defences

Swapboard is a small app where students post textbooks they want to trade. It has a page, a
server and a database, all on a host, and as of Monday it is live: anyone with the address can use
it. On a laptop, the only visitor was its author. Now the visitors are strangers, some of them are
programs rather than people, and nobody is watching the screen. Four things protect an app in that
position, and an agent working on a live app will bring them up by name.

## Rate limit

On Tuesday night a script finds Swapboard's sign-up address and asks it for a new account forty
times a second. Each request is perfectly ordinary; there are just far too many of them, and the
server slows to a crawl for everyone else. A **rate limit** caps how many requests one visitor can
make in a stretch of time, say twenty a minute. Past the cap, the server stops doing the work and
answers with a refusal (status code 429, "Too Many Requests") until the stretch is over. Some hosts
and libraries call this **throttling**.

Don't confuse it with the limits on your hosting plan. An overage is what your host charges when
*your app* uses more than the plan includes. A rate limit is a cap *your app* puts on *a visitor*.

## Input validation

Swapboard's form for posting a book has a title box that won't accept more than 100 characters. On
Wednesday someone skips the form entirely, sends the server a request directly, and the "title" is
five megabytes long. The form's check never ran, because the form was never used. **Input
validation** is the server checking what arrives, before it saves or acts on it, and refusing what
isn't what it expected: too long, the wrong kind of thing, a field that should be there and isn't.
It's also called **server-side validation**, to set it apart from the check in the browser's
form, which is there to help honest visitors fill it in and which anyone can bypass.

## Alert

Swapboard's server log has been recording an error every few minutes since Thursday morning: a
book page that crashes when its photo is missing. The log has it all. Nobody has read the log. An
**alert** is a message that comes to you, by email or text or chat, when something about the live
app crosses a line you set: more than three errors in an hour, say, or no answer at all. The
log is the record; the alert is what tells you to go and look at it. A host's health check is a
neighbour here, and a different thing: it is the host asking your app whether it still answers,
so the host can act. An alert is for you. Setting one up is often called **alerting**.

## Backup

On Friday an agent changes how Swapboard stores its trades, and a mistake in that change empties
the table of books. Rolling back to the last working deploy brings back the old code, but the books
are gone: a rollback restores code, not data. Git history doesn't help either, because the books
were never in the repository; they were only in the database. A **backup** is a copy of the
app's data, kept apart from it, that can be put back after the data is lost; putting it back is
called **restoring** it. For apps like Swapboard the data is the database, so you'll often hear
**database backup**. Many database hosts make one every day on their own, and call it a
**snapshot**. A backup you've never tried restoring is a guess, not a backup.

## Before and after

Two other defences come before an app goes live: keeping secrets out of the repository, and
deciding what a visitor who isn't signed in may do. The deploy-config and sign-in-and-permissions
topics cover those. These four are the ones that matter once it's live and strangers are using it.
