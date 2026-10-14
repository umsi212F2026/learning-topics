# input validation

Answer in two or three sentences, in your own words, with nothing open in front of you.

Lendhaven is a neighbourhood tool library's app where members borrow ladders, drills and saws.
A member borrows a tool by filling in a form on Lendhaven's page, and the form's return-date box
won't let anyone choose a date more than fourteen days away. The form sends the loan to
Lendhaven's server, which saves it in the database. As soon as a loan is saved, the tool shows as
lent out to every other member.

### q-catch-form-check

Lendhaven's builder writes in their notes:

"Lendhaven already has input validation on loan lengths: the form won't let anyone pick a return
date more than fourteen days out."

What is wrong with that?

### q-catch-cleanup-after-saving

The builder asked their agent to keep out loans that are too long. Now a job runs on Lendhaven's
server every night: it looks through the loans saved that day and deletes any whose return date
is more than fourteen days away. The builder writes in their notes:

"Now Lendhaven's server does input validation on loans."

What is wrong with that?

### q-input-validation-vs-form-check

Lendhaven's agent tells the builder: "The borrow form already checks the return date. I'd also
add input validation for it." What is the difference between the form's check and input
validation?
