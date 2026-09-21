# Sort ten claims about what an app's tables are missing

**Used by:** `a-sort-missing-claims`, which serves `c-review-schema`. A study activity: nothing
here can meet the goal.

## The app

You asked your agent to build Potluck, an app for a group of friends who plan dinners together.
Nobody logs in; people just type their name. You described it like this:

1. Anyone can create a dinner with a date, a place, a theme, and the name of whoever is hosting.
   The host's name shows at the top of the dinner's page.
2. On a dinner's page, people sign up to bring a dish. They type their name and the dish, pick a
   course (starter, main, dessert or drink), and can tick "vegetarian".
3. The dinner's page shows how many dishes are signed up for each course, and warns when nobody is
   bringing a main.
4. After the dinner, anyone can give each dish from one to five stars. Each dish shows its average
   and how many people rated it.
5. People can leave comments on a dinner's page. Each comment shows who wrote it and when.
6. A search box on the front page finds dinners by theme.
7. When anyone opens Potluck next week, every dinner, dish, rating and comment is still there.

Before building anything, the agent proposed these tables:

- **dinners:** id, date, place, theme, host
- **dishes:** id, dinner_id, person, dish, course
- **comments:** id, author, text, created_at

## For each claim, answer

Ten classmates each made one claim about what the tables are missing. For each, say whether it's
right (Potluck needs to remember this, and no table holds it) or wrong. If it's wrong, say why.

Then: is anything Potluck has to remember missing from the tables that none of the ten claims
names?

Then say, in one or two sentences, the rule you sorted by.

---

- **k1.** Nothing records whether a dish is vegetarian.
- **k2.** There's nowhere to keep how many dishes are signed up for each course.
- **k3.** The warning when nobody's bringing a main has nowhere to go.
- **k4.** Nothing records who is hosting each dinner.
- **k5.** A comment doesn't record which dinner it was left on.
- **k6.** There's no table of people, so nobody's name is saved.
- **k7.** What people type in the search box has nowhere to go.
- **k8.** Each dish's average star rating needs a column.
- **k9.** Nothing records what time each dinner starts.
- **k10.** Nothing records when each comment was written.

---

## Key, for the tutor

Show the learner everything above this section, not this section. Take all ten answers, the answer
about anything unnamed, and the rule before commenting on any of them.

| claim | right? | why |
| ----- | ------ | --- |
| k1 | right | Point 2 asks for a vegetarian tick, and no column in dishes holds it. |
| k2 | wrong | Worked out: count this dinner's dishes by course. Nothing extra needs keeping. |
| k3 | wrong | Worked out the same way: a dinner with no dish whose course is main. |
| k4 | wrong | It's there, as `host` in dinners. A different name for the same thing. |
| k5 | right | comments has no `dinner_id`, so next week Potluck couldn't tell which dinner's page a comment belongs on. dishes has one, which is why the sign-ups are fine. |
| k6 | wrong | Every name Potluck shows is kept where it's used: `host`, `person`, `author`. A table of people might be tidier, but how the tables are organized isn't the question, and with no logins nothing needs one. Discuss this one as organization rather than holding. |
| k7 | wrong | Nobody expects the search box to still say "tacos" next week. Point 7 lists what must last, and searches aren't on it. |
| k8 | wrong as stated | An average can be worked out, so it needs no column of its own, but only from the stars people gave, and nothing holds those. See the last row. Discuss this one whatever the learner answered. |
| k9 | wrong | Point 1 asks for a date, not a time. Potluck was never asked to keep one, so it isn't missing. |
| k10 | wrong | It's there, as `created_at` in comments. |
| (named by no one) | missing | The star ratings themselves. Point 4 means Potluck has to keep, for each dish, the stars each person gave (or at least a running total and a count), and no table has anywhere for them. This is what k8 was near. If the learner doesn't find it, ask: "where would Potluck keep the three stars Sam gave the lasagne?" |

What's missing, all together: the vegetarian tick (a fact about a dish with no column), which
dinner a comment is on (a link between two kinds of thing), and the ratings (a kind of thing
Potluck keeps several of for each dish, with no table at all).

The rule the learner should arrive at, in words of their own: list what the app must still know
next week; for each, find a column that holds it, under any name; call something missing only if
nothing holds it and it can't be worked out from what is held; leave out what nobody expects back
and what the app was never asked to keep; and don't judge how the tables are arranged.
