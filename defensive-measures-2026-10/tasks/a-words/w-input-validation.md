# input validation

Answer in two or three sentences, in your own words, with nothing open in front of you.

Lanetide is a community swimming pool's app where swimmers book a lane for a swim. A swimmer
books a lane by filling in a form on Lanetide's page, and the form's length box won't let anyone
choose a booking longer than two hours. The form sends the booking to Lanetide's server, which
saves it in the database. As soon as a booking is saved, the lane shows as taken for that time to
every other swimmer.

### q-catch-form-check

Lanetide's builder writes in their notes:

"Lanetide already has input validation on booking lengths: the form won't let anyone book a lane
for more than two hours."

What is wrong with that?

### q-catch-cleanup-after-saving

The builder asked their agent to keep out bookings that are too long. Now a job runs on
Lanetide's server every night: it looks through the bookings saved that day and deletes any
longer than two hours. The builder writes in their notes:

"Now Lanetide's server does input validation on bookings."

What is wrong with that?

### q-input-validation-vs-form-check

Lanetide's agent tells the builder: "The booking form already checks the booking's length. I'd
also add input validation for it." What is the difference between the form's check and input
validation?
