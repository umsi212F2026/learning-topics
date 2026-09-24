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
which shows the four letters of YAGNI on screen, asks the user to type the word for each letter,
and keeps nothing after a reload. The other is a club sign-up app, where six officers, each on
their own phone, need to see who has signed up for an event.

### q-define-spec

Your agent has finished asking you questions about your app and says: "I've written the spec. Read
it and tell me whether it's right before I go any further." Say what a spec is, in your own words,
without just giving it another name.

### q-spec-vs-plan

Your agent writes a spec, you approve it, and then it writes a plan. What is the difference
between those two documents?

### q-spec-describes-finished-code

A classmate says: "I skimmed the spec and approved it. It's the agent's write-up of what it built,
so if the app works when it's done, the spec was fine." What is wrong with what they said?

### q-define-plan

You have approved the spec for your app, and your agent says it will write the plan next and will
not touch any code until you have seen it. Say what a plan is, in your own words.

### q-plan-step-three-done

Your agent says: "The plan has seven steps. Step 3 is done and its checks pass. I haven't started
step 4." Which of these does that tell you?

1. The app is finished, and three of the seven things you asked for work.
2. The app has been built, and the last four steps are yours to test.
3. The plan's seven steps are seven separate features you asked for.
4. One piece of the work is finished and has been checked, four pieces have not been started, and the app as a whole is not done.

### q-plan-first-then-decide

A classmate says: "I had the agent write the plan first. Once I can see the steps, I'll know what
the app is going to be, and I can change it then." What is wrong with what they said?

### q-define-success-criteria

The spec your agent wrote has a section headed "Success criteria", and it asks you to read that
section more carefully than any other before you approve it. Say what success criteria are, in
your own words.

### q-criteria-vs-tests

The spec for your app has success criteria in it, and the app your agent builds also has tests.
What is the difference between them?

### q-criteria-are-features

A classmate says, about the YAGNI app from lab: "My success criteria are that it shows the four
letters, that there's a text box next to each letter, and that there's a Check button." What is
wrong with what they said?

### q-define-constraint

Before it designs anything, your agent asks you a run of questions: who will use the app, on what
devices, when you need it by, and whether anyone will look after it once the term ends. It says
your answers are the constraints it will be working with. Say what a constraint is, in your own
words.

### q-constraint-vs-requirement

What is the difference between a constraint on an app and a requirement of it?

### q-constraint-rules-out

Your agent says: "Two of the three approaches I was going to show you are out. You told me the six
officers have to be able to open this on their phones without installing anything, and both of
those need an app installed." Which of these does that tell you?

1. The agent prefers the one approach that is left and is arguing for it.
2. Something you told it about the situation is a limit the app has to fit inside, and it takes those two approaches off the table rather than counting against them.
3. Those two approaches would not work, for any app.
4. You should change what you told it, so that all three approaches stay available to you.

### q-define-mvp

Your idea for Problem Set 2 has grown to eleven things the app should do, and your agent says the
first thing to settle is what the MVP is. Say what an MVP is, in your own words, without spelling
out what the letters stand for.

### q-mvp-vs-prototype

Your agent offers to build either an MVP of your app or a prototype of it first. What is the
difference?

### q-mvp-is-whatever-fits

A classmate says: "The MVP is however far the agent gets before the lab ends. I'll just let it
build until the clock runs out, and whatever exists then is the MVP." What is wrong with what they
said?

### q-define-yagni

The app you built in lab tests whether someone can say what YAGNI stands for. Leave the four words
aside: say what the idea called YAGNI tells you to do when an app is being designed, and why.

### q-yagni-vs-keep-it-simple

"Keep it simple" and YAGNI are both advice about not overdoing an app. What is the difference
between them?

### q-yagni-cheaper-now

A classmate says, about the YAGNI app from lab: "The agent offered to add a scoreboard that
remembers your past scores after a reload. The brief said the app doesn't need to remember
anything, but I said yes, because it's only a few extra lines now and it would cost more to add
later." What is wrong with what they said?

### q-define-spike

Your agent says: "I don't know yet whether a page in the browser can read a file straight out of
Google Drive with no server involved. Let me do a spike." Say what a spike is, in your own words.

### q-spike-vs-prototype

Your agent can spend twenty minutes on a spike or on a prototype. How is a spike different from a
prototype?

### q-spike-twenty-minutes

Your agent says: "Before I put this in the plan, give me twenty minutes on a spike. I want to know
whether a browser can read a file straight out of Google Drive with no server. I'll throw away
whatever I write." What is it telling you?

### q-define-architecture

Your agent presents its design for your app a section at a time, and the first section is headed
"Architecture". Say what that section is going to be about, in your own words.

### q-architecture-vs-stack

An agent's design for your app names its architecture and, separately, its tech stack. What is the
difference between the two?

### q-architecture-shared-list

Your agent says: "Right now the page keeps the sign-up list inside the browser it was made in, and
nowhere else. For all six officers to see the same list, there has to be something outside the
browser holding it, and the page has to ask that for the list and tell it about every change.
That's an architecture change, not a setting." Which of these does that tell you?

1. The app would gain a new part outside the browser that holds the list, and the page would have to talk to it, so the app's parts and how they fit together change rather than one of its settings.
2. The app would have to be rewritten in a different programming language.
3. The six officers' browsers would send the list to each other directly, with nothing in between.
4. It is a matter of finding the right option and switching it on, which the agent can do quickly.

### q-define-tech-stack

Two classmates built apps that do much the same things and look much the same on screen, and your
agent says the two apps have different tech stacks. Say what a tech stack is, in your own words,
without just giving it another name.

### q-stack-says-who-does-what

A classmate says: "My agent listed my app's tech stack as React, Vite and a SQLite database, so
now I know which part of my app is responsible for what." What is wrong with what they said?

### q-same-stack-two-approaches

Your agent says: "Both approaches use the same tech stack. What differs is where the list lives.
In the first, it only exists in the browser of whoever made it. In the second, it's held on a
server that everyone's browser asks." What is it telling you?

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

### q-which-reason-fits

For that same club sign-up app, where six officers each on their own phone need to see the same
list and it has to keep working for next year's committee, four classmates all picked the shared
list. Whose reason is a reason about this app?

1. "It's the one the agent recommended, and it explained itself well."
2. "A shared list scales better, and scaling is always worth paying for."
3. "All six officers have to see the same sign-ups on their own phones, and a list kept in one person's browser can't be seen from the other five."
4. "Our club has been going since 1974, so we should build it on something solid."
