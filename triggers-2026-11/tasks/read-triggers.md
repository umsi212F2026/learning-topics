# What starts a workflow, and where its work waits

The last reading followed a teaching assistant designing a grading workflow. This page takes up
one more design decision from its list, what triggers a run, and a question that comes with it:
where the work waits until something is ready to do it.

The TA still grades about 200 homework submissions a week. Homework is due Friday at midnight, and
most submissions arrive in the last few hours before that.

## Three kinds of trigger

Every run of a workflow starts because something started it. There are three kinds of trigger.

- **A person.** The TA sits down on Saturday morning and starts the grading run by hand.
- **A schedule.** The run starts at set times: every night at 2 a.m., or every Saturday at 9 a.m.
- **An event.** The run starts because something happened. If grading began the moment a student
  submitted, the TA's workflow would be **event-driven**.

None of them is best everywhere. Each helps some goals and hurts others.

- **Timeliness.** An event trigger can start a run within minutes of a submission. With a
  Saturday schedule, everyone waits until Saturday. A person trigger is as timely as the person.
- **People's effort.** A person trigger costs someone's attention every time, and the run doesn't
  happen when they forget. A schedule or an event costs effort once, when it is set up.
- **The cost of runs that find nothing to do.** A schedule fires whether or not there is work. A
  grading run every hour would find nothing to grade most of the week. An empty run costs little
  if it is a program glancing at a folder, and more if it wakes an agent that reads everything to
  decide that nothing has changed. An event trigger runs only when there is something to do.

Which matters most depends on facts about this workflow: how soon its result is needed, how often
there is work, who would have to remember to start it, and whether the machine or person that does
the work will be available when the trigger fires. For the TA, nobody needs feedback before the deadline, and
nearly all the work arrives in one burst, so one scheduled run on Saturday morning fits. A course
where students resubmit all week and want quick feedback would push toward an event.

## Noticing an event

An event trigger needs some way to find out that the event happened. There are two.

**Checking again and again.** A program looks at the course site every ten minutes and asks: any
submissions I haven't seen? This is **polling**. It is easy to set up, since all it needs is a way
to look. But most looks find nothing, each costs a little, and a submission can wait ten minutes
to be noticed. Polling is a schedule doing an event trigger's job.

**Being told.** Some tools and services let you name a command to run when something happens
inside them. That arrangement is a **hook**. Git, for example, can run a command of yours every time you
make a commit. A service on the web usually tells you by sending a message to a web address you
gave it, and then the hook is called a **webhook**: the course site might send one each time a
student submits. Being told is quicker than polling and wastes nothing on empty looks. But the
service has to offer a hook, and something has to be ready to receive the message.

## Schedules, and the laptop problem

On Mac and Linux, the usual way to run something at set times is a **cron job**. Tell your agent
"set up a cron job to run the grading script at 9 a.m. every Saturday," and it adds one line to a
table the operating system keeps. Your script isn't sitting there all week waiting: on Saturday at
9 the system starts it, and when it finishes it is gone. On a Mac, your agent may use the Mac's
own scheduler, launchd, instead.

A schedule on your own laptop fires only if the laptop is on and awake at that time. If the TA's
laptop is turned off at 9 a.m. on Saturday, the cron job simply doesn't run that week. (A laptop
that is only asleep is different on a Mac: launchd runs a job it missed during sleep once the Mac
wakes, though not one missed while the Mac was turned off. cron runs neither.) A hook that runs a
command on the laptop has the same problem: if the event happens while the laptop is off or
asleep, nothing runs. A person can be unavailable too. If the TA has to approve each student's
feedback before it is sent, and is away the weekend the run fires, the feedback sits unsent until
they are back. So pick a time when the machine is reliably on, or let a person start the run, or
make sure a missed run's work is still waiting for the next one. Where else a workflow could run
comes in a later topic.

## Where the work waits

A trigger says when a run starts, not what it should work on. Submissions arrive at all hours, but
the worker, whatever does the grading, is ready only some of the time. In between, the work waits
somewhere, and the worker needs a way to find it. That is the **work queue**, a term this page
uses loosely. There are three common kinds.

- **A queue the workflow keeps.** Each time a submission arrives, a program adds it to a waiting
  list, and the grading run takes items off as it grades them. That program has to be running
  when each submission arrives.
- **A source that already holds the waiting work.** The course site keeps every submission and
  when it arrived. The grading run can ask the site for everything since the last run, and nothing
  extra is kept.
- **A list worked out each time from the state of files.** Each graded submission gets a grade
  file next to it, so any submission with no grade file is still waiting. Nobody keeps a list; the
  run works it out by looking.

A queue can also be worked out from a log. If the workflow logs a line each time it finishes a
submission, the work still waiting is every submission not in the log. The log records what
happened, and the queue comes from it; they needn't be two records.

**The worker taking work from a queue has a trigger of its own.** Putting work on a queue doesn't
get it done. Something still has to start the worker: the TA by hand, a cron job, or an event such
as a new item arriving. A common combination is an event that adds each submission to the queue as
it arrives, and a schedule that starts the worker. Then a run missed because the laptop was off
loses nothing: the work is still waiting, and the next run picks it up.

A queue also spreads work out. If 150 submissions in the last two hours each started an agent run
at once, that is 150 runs together, and an agent's provider may limit how many requests it takes
in a minute. With a queue, the worker takes them one at a time.

## When there's no queue

Without a queue, each piece of work goes straight to the worker when it arrives and has to be
taken up then. That is fine in two situations. One is a worker that is always available and never
overloaded: a quick program on a machine that is never off, with a few items an hour. The other is
a workflow where dropping some work is acceptable: if a program updates a count of submissions on
a page the TA glances at, a missed update is fixed by the next one.

Outside those two, a workflow with no queue loses work. A submission that arrives while the
laptop is off is never graded, and nobody notices until the student asks.

## Putting it to use

Once these decisions have names, they are easy to tell an agent: "poll the course site every
fifteen minutes," "treat any submission with no grade file as waiting." Each is a design decision,
made on purpose.
