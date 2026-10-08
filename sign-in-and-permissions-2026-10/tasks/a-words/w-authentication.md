# Authentication

Answer in two or three sentences, in your own words, with nothing open in front of you.

Pantry is a recipe box for a campus cooking club. Members sign in through GitHub, post recipes, and
may edit or delete only the recipes they posted.

### q1

On every request to delete a recipe, Pantry's server compares the signed-in user with the recipe's
author and refuses if they differ. A student writes in the project notes:

"This check is Pantry's authentication."

What is wrong with that?

### q2

Pantry keeps no passwords: its `users` table holds each member's GitHub id, name and picture, and
nothing else. A student says:

"Pantry doesn't do any authentication. GitHub handles sign-in, and we never check a password
ourselves."

What is wrong with that?
