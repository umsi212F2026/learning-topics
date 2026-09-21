# Judge ten traces of actions in a reading-list app

**Used by:** `a-judge-action-traces`, which serves `c-trace-action`. A study activity: nothing
here can meet the goal.

## The app

Your agent built Shelf, a reading list, and summed it up like this:

> Shelf has three parts: a page that runs in your browser, a server that runs on your laptop, and
> a SQL database the server keeps its data in. While you're developing it, the page itself comes
> from the dev server at http://localhost:5173, and the server is at http://localhost:3001. The
> page sends its requests straight to the server, and only the server talks to the database. The
> page gets your books from the server when it loads; after that it works out whatever it shows
> from what it already has, and sends the server a request only when something that's kept
> changes.

What you can do in Shelf:

- Type a title in the box and click Add. The book appears at the bottom of the list.
- Tick a book's Finished box.
- Flip the "Hide finished" switch to hide finished books from the list. The switch is always off
  when the page loads.
- Under the list, a line says how many books are finished, such as "3 of 7 finished".
- Shelf keeps your books and which ones are finished: close everything, come back tomorrow, and
  they're all there.

## The actions

- **A.** With Shelf open, you type "Middlemarch" and click Add. It appears at the bottom of the
  list.
- **B.** You flip "Hide finished" on. The finished books disappear from the list.
- **C.** You reload the page. Your books appear.

Below are ten traces that students wrote, each for one of the three actions. A trace passes when
it names every part the action goes through, in order, on the way there and on the way back to
the screen; names no part the action doesn't go through; and gives no part a job it couldn't do.

## For each trace, answer

1. Does it pass? Yes or no.
2. If no, the one thing wrong with it: a part (or a step between two parts) is missing; a part is
   named that the action doesn't go through; the parts are out of order; or a part is given
   something it couldn't do.

When you've done all ten, say in one or two sentences the rule you judged by. Then rewrite two of
the traces that failed so that they pass.

---

### Action A: add "Middlemarch"

#### a1

> The page hears the click and sends the server a request to save a new book called
> "Middlemarch". The server asks the database to store it. The database stores it and tells the
> server it's done, with the new book's number. The server sends the page a response saying it
> worked, with the saved book in it. The page adds the book to its list, and it appears at the
> bottom.

#### a2

> The page sends "Middlemarch" to the server, the server saves it in the database, and it shows up
> at the bottom of the list.

#### a3

> The page saves "Middlemarch" in the database. Then it asks the server for the updated list, the
> server sends the list back, and the page shows it.

#### a4

> The page sends the title to the server, which passes it to the database. The database stores it
> and sends the new book back to the page, which puts it at the bottom of the list.

#### a5

> The page sends the title to the dev server at localhost:5173, which passes it on to the server at
> localhost:3001. The server asks the database to store it, and the database says it's done. The
> server sends a response back to the page with the saved book, and the page adds it to the list.

#### a6

> The page sends a request to the API. The API passes it to the server, which asks the database to
> store the book. The database tells the server it's stored, the server sends the saved book back
> to the page, and the page adds it to the list.

### Action B: flip "Hide finished" on

#### b1

> Nothing leaves the page. The page already has every book and knows which are finished, so it
> just stops showing the finished ones. The server and the database aren't involved.

#### b2

> The page asks the server for only the unfinished books. The server asks the database for them,
> the database sends them to the server, the server sends them to the page, and the page shows only
> those.

### Action C: reload the page

#### c1

> The browser asks the dev server at localhost:5173 for the page, and the dev server sends the
> page's files. The page starts with no books, so it sends the server a request for them. The
> server asks the database for all the books, and the database sends them to the server. The
> server sends them to the page in a response, and the page puts them on screen.

#### c2

> The page asks the server for the books. The server gets them from the database and sends them
> back, and the page shows them.

---

## Key, for the tutor

Show the learner everything above this section, not this section. Take all ten answers and the
stated rule before saying anything about any of them.

| trace | passes? | what decides it |
| ----- | ------- | --------------- |
| a1 | yes | Every part in order both ways (page, server, database, server, page), with what passes at each step, and the page, not anything else, changes the screen. |
| a2 | no | The way back is missing. Nothing says the database told the server, or that the server answered the page, so "it shows up" has no cause: a page that never heard back couldn't know the book was saved. The near miss is a1. |
| a3 | no | The page is given something it can't do: only the server talks to the database. Asking the server for the list afterwards would be plausible in some other app, but the first step is impossible here. |
| a4 | no | The database is given something it can't do: it answers the server, never the page. |
| a5 | no | Names a part the action doesn't go through. The page's requests go straight to the server; the dev server's only job was sending the page's files when it loaded. Set it beside c1, where the dev server really is on the path. |
| a6 | no | Names something that isn't a part. The API is the set of requests the server answers (here, one of them is "save this book"), not a stop between the page and the server. "The page sends a request to the server's API" would be fine; "the API passes it to the server" makes it a separate thing. Discuss this one whatever the learner answered. |
| b1 | yes | The switch isn't kept, and the page already has every book and knows which are finished, so the action never leaves the page. Naming no other part is exactly right. |
| b2 | no | Names parts the action doesn't go through. The description settles it: the page works out what it shows from what it already has, and the switch isn't kept. In some other app a filter might ask the server; not in this one. |
| c1 | yes | A reload does go through the dev server, because the page's files come from it. Then the page, starting empty, asks the server, and the rest is the way there and back. |
| c2 | no | Misses a part. Before the page can ask for anything, the browser has to get the page again, from the dev server. Set it beside a5: the dev server is on the path for a reload and not for an Add. |

Three pairs are built to be compared if either of a pair is misjudged: a1 and a2 (the way back),
a1 and a5 (the dev server on an Add), c1 and c2 (the dev server on a reload).

The rule the learner should arrive at, in words of their own: a trace passes when it names each
part the action reaches, in the order it reaches them, on the way there and on the way back to the
screen; names nothing the action doesn't reach; and has each part do only what it can (the page
draws the screen and talks to the server, the server talks to the page and to the database, the
database talks only to the server). A good rewrite of a2 adds the way back; of a5, removes the dev
server; of c2, adds it.
