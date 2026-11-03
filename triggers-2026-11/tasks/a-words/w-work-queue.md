# Work queue

### vs-log

A photographer drops new photos into a folder called `incoming`. Every night a script resizes
them. Each time it finishes a photo, it writes that photo's name as a new line in a file called
`done.txt`. To decide what to resize, the script picks every photo in `incoming` whose name is
not in `done.txt`.

In this workflow, what functions as a log, and what functions as a work queue? Answer in two or
three sentences, in your own words.

### catch-pick

A tutoring center takes bookings through a booking site, which keeps every booking and when it
was made. Every evening at 8, a script asks the booking site for the bookings made since the
script's last run, and emails each tutor their new sessions.

In this workflow, what is the work queue?

1. The script's sent-mail folder
2. There is none, since nobody keeps a list of waiting bookings
3. The bookings returned to the script by the site
4. The 8 p.m. schedule

### catch-shipped

A small online shop's packing script writes each order number into a file called `shipped.txt`
once that order has been packed and sent. The owner says:

"`shipped.txt` is our work queue."

What is wrong with that? Answer in two or three sentences, in your own words.
