# Hook

### vs-event-driven

A community garden collects volunteer sign-ups through an online form service, and wants each new
volunteer added to the schedule soon after they sign up. It is choosing between two set-ups.

- **Set-up A.** The coordinator enters a web address in the form service's settings, and the
  service sends a message there each time someone submits the form. The coordinator's program
  then adds that volunteer.
- **Set-up B.** The coordinator's program asks the form service every ten minutes for any new
  sign-ups, and adds each one it finds.

Is each statement true or false?

#### a

"Set-up A uses a hook."

1. True
2. False

#### b

"Set-up A is event-driven."

1. True
2. False

#### c

"Set-up B uses a hook."

1. True
2. False

#### d

"Set-up B is event-driven."

1. True
2. False

### catch-pick

Which of these uses a hook?

1. A script checks a shared inbox every five minutes for new mail
2. Git runs a writer's backup command each time she makes a commit
3. A cron job copies a writer's notes to a backup drive at 1 a.m.
4. A writer runs her backup command herself after each writing session

### catch-weather

A farm wants to know as soon as the weather service issues a storm warning for its county. The
farm manager says:

"We set up a hook on the weather service: every hour our script asks the service whether a storm
warning has been issued."

What is wrong with that? Answer in two or three sentences, in your own words.
