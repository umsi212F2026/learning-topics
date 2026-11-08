# Rubric: Append-only

If the learner misses a question here, set a DEFINE or INTERPRET move for append-only live, as help
(it is recorded as helped and doesn't count), then come back to a production question.

An append-only store is only ever added to, so nothing already in it is changed or removed. The
classic one is a log: each new line goes at the end, and nobody edits yesterday's lines. Append-only
is about writing, and says nothing against reading: anyone may read an append-only store. Being able
to add is not enough; once anything already there is changed or deleted, the store is not
append-only. Read-only is the course's contrast: a read-only user may not write at all, neither
adding nor changing. An append-only writer writes, but only new records.

### vs-read-only

- **goal:** `w-append-only`
- **move:** DISTINGUISH
- **type:** compound
- **tutor note:** the program's access to the watering record is append-only: it adds lines and
  never changes or removes one. Its access to the plant list is neither: it changes a plant's room
  in place, so it is editing, which is not append-only, and it writes, so it is not read-only. A
  learner who calls the record read-only may be reading "nothing is changed" as "nothing is
  written"; ask what the program does after a plant is watered. One who calls the plant list
  append-only may think any store the program writes to is append-only; ask what happens to the old
  room when a plant moves. One who calls it read-only may be thinking of how Odette looks at it;
  ask what the program does when she moves a plant.

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 3

### catch-pick

- **goal:** `w-append-only`
- **move:** CATCH
- **type:** mcq
- **answer:** 3
- **credit:** full for 3 only. The program adds a line per ride and no line is ever changed or
  removed, so the log is append-only, and members reading it changes nothing about that. Choice 1
  reads the term as its confusable: members who only read have read-only access, since they add
  nothing. Choice 2 stretches the term past what it names: deleting old lines is removing what is
  already there, so the log would no longer be append-only. Choice 4 takes append-only as a limit on
  reading; it limits only how the store is written.

### catch-groceries

- **goal:** `w-append-only`
- **move:** CATCH
- **answer:** Being able to add to the list doesn't make it append-only. Items are deleted once they
  are bought, and an append-only store is one where nothing already in it is ever changed or
  removed. So this list is edited, not append-only.
- **credit:** full for naming that items already on the list are deleted, and that append-only means
  nothing already there is changed or removed, so adding alone doesn't make it append-only. Half for
  "items get deleted" with nothing on why that rules out append-only, or for "append-only means you
  can't delete" with nothing tying it to this list. None for a different quibble alone, such as
  that the family should keep a record of what they bought.
- **tutor note:** a learner who agrees, since adding is what append means, has the half of the term
  about adding and is missing the half about leaving old records alone; ask what happens to an item
  after it is bought.
