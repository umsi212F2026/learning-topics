# The words of software design

**Intended goals:** `w-spec`, `w-plan`, `w-success-criteria`, `w-constraint`, `w-mvp`, `w-yagni`,
`w-spike`, `w-architecture` and `w-tech-stack`, with four questions on `c-write-success-criteria`
and `c-choose-approach` at the end.

Answer each question in one to three sentences, in your own words, with nothing open. The last
four ask for a little more and say so. Where a question quotes an AI coding agent, imagine it is
designing an app with you before it builds anything: it asks you about the app one question at a
time, offers you two or three approaches with their trade-offs and usually recommends one, shows
you its design a section at a time for approval, writes a spec you are asked to review, and only
then writes a plan and starts building. Two apps turn up more than once. One is the app from lab,
which shows the five letters of YAGNI on screen, asks the user to type the word for each letter,
and keeps nothing after a reload. The other is a club sign-up app, where six officers, each on
their own phone, need to see who has signed up for an event.

### q-criteria-for-practice-signup

A club officer asks you for an app: "Every week I post in the group chat asking who's coming to
Thursday practice, and I end up counting replies across three different threads, and I still get
it wrong." In one sentence, say what this app is for. Then write two success criteria for its
spec, each one that a person who has never heard of the club could settle by using the finished
app.

### q-rota-meets-and-misses

Someone says their chore rota app is for making sure nobody in the house feels they do more than
their share, and writes three success criteria for it: that every chore in the house appears in
the list; that each chore shows the name of the person whose turn it is; and that a housemate can
tick a chore off once they have done it. Describe an app that a hurried but honest builder could
ship that meets all three and still misses what the app is for, and give one more criterion that
would catch it.

### q-choose-signup-approach

Your club's sign-up app: six officers, each on their own phone, all need to see who has signed up
for an event, and the app has to keep working for next year's committee. The club was founded in
1974 and its colors are green and gold. Your agent offers two approaches and recommends the first.
Approach A, list on one device: the list is kept in the browser of whoever made it, there is
nothing to set up and nothing to sign in to, and it works with no internet. Approach B, shared
list: the list is kept on a server that every browser asks, so everyone with the link sees the
same list, and it needs a server somebody keeps running. Say which you pick, what that pick gives
up, and why.


