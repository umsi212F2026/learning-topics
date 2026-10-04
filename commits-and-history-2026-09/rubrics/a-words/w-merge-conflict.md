# Rubric: merge conflict

### q-conflict-vs-error

- **type:** free
- **goal:** w-merge-conflict
- **move:** DISTINGUISH
- **answer:** an error means something failed or went wrong. A merge conflict is git stopping on
  purpose because both sides changed the same lines and it will not choose between the two changes.
  Nothing is broken: the merge is paused, waiting for someone to decide what those lines should say,
  and it can finish once they do.
- **credit:** full credit for saying a conflict is git deliberately stopping so someone can choose
  between two changes to the same lines, and not something having failed or broken. Full credit for
  "a conflict needs someone to decide" without saying it is not a failure. Half credit for "nothing is
  broken" without saying why git stopped. No credit for "a conflict is a kind of error that happens
  when two people edit a file", or for incidental differences such as the wording or colour of the
  message.

### q-conflict-different-files

- **type:** free
- **goal:** w-merge-conflict
- **move:** CATCH
- **answer:** changes to different files do not conflict: git combines them on its own. A merge
  conflict needs both sides to have changed the same lines of the same file, so these two changes
  could not by themselves cause one.
- **credit:** full credit for saying different files combine without a conflict, because a conflict
  needs both sides changing the same lines. Do not accept a different quibble as the error: that
  they should have pulled sooner, that README.txt should not be edited, or that the agent should
  have rebased.

### q-git-picks-newer

- **type:** free
- **goal:** w-merge-conflict
- **move:** CATCH
- **answer:** git does not choose between two changes to the same lines, by date or in any other way.
  That is exactly where it stops: a merge conflict is the place git refuses to choose, and someone
  has to decide, either a person or their agent.
- **credit:** full credit for saying git does not pick a side but stops and leaves the choice to a
  person (or to the agent, with the person). An answer saying git cannot tell which is newer counts
  only if it also says git stops instead of choosing. Do not accept a different quibble as the error:
  that the instructor's change should win, that conflicts are rare, or that "newer" is hard to
  define.

### q-what-makes-conflict

- **type:** mcq
- **goal:** w-merge-conflict
- **move:** DEFINE
- **answer:** 2
- **credit:** 1 is two different files, which combine on their own. 3 is a file only one side has,
  which comes in without a conflict. 4 involves the editor, not a merge: unsaved edits are invisible
  to git and are not one of the two changes a conflict is between.
