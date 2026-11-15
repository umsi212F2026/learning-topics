### separate-user

Olu is choosing his classes for next term, and one step of his workflow gathers what other students have written about them.

- Each night the review fetcher, a program Olu wrote, reads his shortlist of courses, which he typed, downloads the reviews of those courses from a course review site, and saves them in a folder called reviews.
  - His home folder holds the shortlist, the reviews folder, a thesis folder with the chapters he has written so far, and a settings file with his university login.
  - It is given no login, key or token, since reading the review site doesn't require one.

The harm Olu is worried about: a bug in the review fetcher makes it overwrite the chapters in his thesis folder.

His agent proposes: 'I can run the review fetcher as a separate user you set up for it, given only the shortlist, read-only, and the reviews folder, and still able to reach the course review site.'

#### a

Would this limit significantly reduce the risk of this harm?

1. Yes
2. No

#### b

Could the review fetcher still do its work under this limit?

1. Yes
2. No
