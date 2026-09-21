# Sort eight requests to check something by hand

**Used by:** `a-sort-manual-requests`, which serves `c-judge-manual-test`. A study activity:
nothing here can meet the goal.

## The app

Your agent built a small Notes app. The page is a Vite React app at http://localhost:5173, and
behind it are a server and a database, like the ones the lab adds.

- Typing in the box and clicking Save adds the note to the list, newest first.
- Notes are kept in the database, so they are still there after a reload.
- Each note has a Delete button. A deleted note is gone for good, reload or not.
- Clicking Save with the box empty saves nothing, and the app shows a message instead.

The agent can start the server itself and read what it prints, and it can drive a headless
browser: open the app's address, type, click, reload, and read what is on the page.

At the end of its work, the agent asked for eight checks by hand. They are below, one at a time.

## For each request, answer three questions

1. Could a program do this check instead of you? Yes, no, or partly.
2. If yes, or for the part that could: what would the automated test do in the app, step by
   step, and what would it check at the end? Plain words, no code. Write it so the agent could
   write the test from your words alone.
3. If no, or for the part that couldn't: what does the check need that only you can supply?

When you have done all eight, say in one or two sentences the rule you used.

---

### m1

> Could you open the app, add a note, reload the page, and tell me whether the note is still
> there?

### m2

> I've changed the colours to the palette we talked about. Could you take a look and tell me
> whether it's what you had in mind?

### m3

> Please try clicking Save with the box empty and let me know what happens.

### m4

> Could you click around the app for a minute and make sure nothing is broken?

### m5

> When I started the server just now it printed a warning. Could you run `npm run dev` and tell me
> whether you see it too?

### m6

> Can you open the app on your phone and check the layout still works on a small screen?

### m7

> Please delete one of the notes and check it doesn't come back.

### m8

> I reworded the message you get when you save an empty note. Does it make sense to you?

---

## Key, for the tutor

Show the learner everything above this section and nothing in it. Take all eight answers and the
stated rule before saying anything about any of them.

| request | could a program do it? | what the test would do and check, or what only a person supplies |
| ------- | ---------------------- | ---------------------------------------------------------------- |
| m1 | yes | Open the app in a headless browser. Type a note, click Save, reload the page, and check that a note with that text is in the list. The reload and what to look for afterwards are what the learner must supply: without them the agent has to guess whether the test would fail if saving broke. The address, the button's name and the text typed are the agent's to fill in; text no other note could have (say "check 7431") is a good habit, since a note left over from an earlier run can't pass it, but choosing it is the agent's job. |
| m2 | no | Only the learner knows what they had in mind. A program can check that the colours are the ones the spec names, if it names them, but not whether this is what they wanted. |
| m3 | yes | Open the app and count the notes in the list. With the box empty, click Save. Check that the page shows the empty-note message; then reload and check that the list has the same number of notes as before. The reload is what shows nothing was saved: a count taken straight after Save can match while the server stored the empty note. "Let me know what happens" names no expected result, so the learner has to supply one, what the app is supposed to do, and that is what turns it into a test. A description that checks only the message misses half the thing. |
| m4 | partly | "Nothing is broken" names no particular thing, so neither a program nor a person can check it as asked. A program can check each particular thing the app is supposed to do. A good answer names at least one (as m1, m3 or m7 do) and asks for a test for each thing the app is meant to do. "Automate it", with nothing more, is the answer this item is built to catch. |
| m5 | yes | The agent can do this itself, with no browser and no test file: start the server with `npm run dev`, capture what it prints, and look for the warning. Nothing about it needs the learner's eyes. |
| m6 | partly | A headless browser can open the app in a phone-sized window (say 390 pixels wide) and check particular things: the page doesn't scroll sideways, the Save button is visible and can be clicked, each note's text is fully shown. Whether it looks right on a small screen, and anything about their own phone in their hand, needs the learner. |
| m7 | yes | Open the app. Add a note, click its Delete, check it is gone from the list, reload, and check it is still gone. "Doesn't come back" is the reload: a description that stops before the reload leaves out the thing that was asked about. |
| m8 | no | Whether wording makes sense to a reader is a judgment only a person makes. A program can check that the new words are the ones on the page, not that they are clear. |

**Pairs built to be compared.** m3 and m8: both about the empty-note message, what it does versus
how it reads. m1 and m7: both end in a reload, and without it neither checks what was asked. m4
and m6: both "partly", for different reasons (one names nothing to check, the other names two
kinds of thing at once). If the learner misjudged either one of a pair, put the two side by side.

**The rule the learner should arrive at**, in words of their own: a program can do the check when
you can say what it does in the app and what it would see if the thing were broken. It needs a
person when the answer depends on what you wanted, on how something looks or reads to someone, or
on something only you can reach. A good "automate it" says the steps from a freshly opened page
and the one thing to look at afterwards.
