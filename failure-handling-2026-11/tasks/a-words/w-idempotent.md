# Idempotent

### vs-deterministic

#### a

Hana keeps a journal in a folder of text files. Each night a program goes through the folder, and for each entry that has no summary yet, it asks an agent to write a three-line summary. The agent words each summary differently every time it is asked. The program saves a summary only once the agent has finished it, and it skips any entry that already has a summary.

Which best describes Hana's summary step?

1. Idempotent, but not deterministic
2. Deterministic, but not idempotent
3. Both
4. Neither

#### b

A chess club keeps members' balances in a sheet. On the first of each month, a program adds $20 of dues to every member's balance. It does the same arithmetic every time and never asks an agent anything. It doesn't record anywhere that this month's dues have been added.

Which best describes the club's dues program?

1. Idempotent, but not deterministic
2. Deterministic, but not idempotent
3. Both
4. Neither

### catch-pick

Each evening, a program adds a row to Theo's training sheet for each workout in that day's export from his watch. It doesn't look at what is already in the sheet. Last night it stopped after adding three of the day's six workouts.

Which of these uses the term idempotent correctly?

1. The step is idempotent, since the same export always gives the same rows.
2. An idempotent step would leave the sheet unchanged, so this one can't be.
3. It isn't idempotent because it stopped; one that never stops would be.
4. It isn't idempotent: a rerun would add the first three workouts again.

### catch-weekly-email

Jun tracks his spending in a sheet. Every Sunday evening, a program reads the sheet, without changing anything in it, and emails Jun a summary of the week's spending. Jun says:

"That step is idempotent, since it only reads the sheet and never changes it."

What is wrong with that? Answer in two or three sentences, in your own words.
