# Hook

### vs-event-driven

A public library collects volunteer sign-ups through an online form service, and wants each new
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

A writer has set up Git so that each time she makes a commit, Git runs her command that copies
her notes to a backup drive.

Which of these uses the word "hook" correctly?

1. "The hook is the backup drive, where the notes end up."
2. "It's a hook because it runs with no person starting it."
3. "The hook is Git running her command each time she commits."
4. "It would still be a hook if her script asked Git every hour for new commits."

### catch-weather

A farm wants to know as soon as the weather service issues a storm warning for its county. The
farm manager says:

"We set up a hook on the weather service: every hour our script asks the service whether a storm
warning has been issued."

What is wrong with that? Answer in two or three sentences, in your own words.
