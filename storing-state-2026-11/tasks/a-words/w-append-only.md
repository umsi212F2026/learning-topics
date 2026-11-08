# Append-only

### vs-read-only

Odette runs a small program on her laptop that keeps track of her houseplants. It keeps a plant
list with each plant's name and the room it sits in, and when she moves a plant, the program
changes that plant's room in the list. When she waters a plant, the program adds a line to a
watering record with the date and the plant. No line already in the record is ever changed or
removed.

#### a

Which term best describes the program's access to the watering record?

1. Append-only
2. Read-only
3. Neither

#### b

Which term best describes the program's access to the plant list?

1. Append-only
2. Read-only
3. Neither

### catch-pick

A cycling club keeps a ride log. After each group ride, a program adds a line with the date, the
route and who rode. No line is ever changed or removed, and members open the log to look back at
past rides.

Which of these uses the term append-only correctly?

1. Since members only ever read the log, it is append-only for them.
2. The program could delete last year's lines and the log would stay append-only.
3. The log is append-only: rides are added, and old lines are left as they are.
4. Because the log is append-only, members can't open it to read past rides.

### catch-groceries

A family keeps its grocery list in a shared document. Anyone in the family adds an item when they
notice it is running low, and whoever does the shopping deletes each item once it is bought. One of
the parents says:

"Our grocery list is append-only, since anyone can add to it."

What is wrong with that? Answer in two or three sentences, in your own words.
