# Rubric: Least privilege

If the learner misses a question here, set a DEFINE or INTERPRET move for least privilege live, as
help (it is recorded as helped and doesn't count), then come back to a production question.

Least privilege is giving each part of a workflow only the access it needs, and no more. It is a
choice made when access is handed out, measured against the job: a part that needs to touch two
things gets both, and one that needs to write gets to write. Authorization is the course's
contrast: deciding what someone may do, whether in setting permissions or in checking them when
something tries to act. Authorization is any such decision; least privilege is the principle that
says how much it should allow. A program can be fully authorized to do far more than it needs, and
then least privilege is broken.

### vs-authorization

- **goal:** `w-least-privilege`
- **move:** DISTINGUISH
- **type:** compound
- **tutor note:** the laptop deciding, at the moment the program tries to delete, whether it may is
  authorization. Jun's choice follows least privilege: sorting photos into albums needs reading the
  photos and adding album entries, and never deleting a photo, so he gave the program exactly what
  its job needs and no more. A learner who calls the laptop's decision least privilege may be
  reading the term as whatever enforces limits; ask what decided which permissions the program
  had. One who says No to part b may think withholding delete is too restrictive; ask what sorting
  into albums needs. One who says No because the program later tried to delete may be judging the
  choice by the program's behavior; ask whether that delete was part of sorting.

#### a

- **type:** mcq
- **answer:** 1

#### b

- **type:** mcq
- **answer:** 1

### catch-pick

- **goal:** `w-least-privilege`
- **move:** CATCH
- **type:** mcq
- **answer:** 2
- **credit:** full for 2 only. The agent's job is to read photos and write captions, and it can do
  exactly that and nothing more: least privilege. Choice 1 reads the term as "as little as
  possible": writing captions is the agent's job, so the access it needs is no breach. Choice 3
  stretches the term to a fixed count; the agent needs two things here and gets both. Choice 4 reads
  the term as its confusable: the check made each time is authorization, while least privilege is
  the principle for how much to grant.

### catch-newsletter

- **goal:** `w-least-privilege`
- **move:** CATCH
- **answer:** Being authorized only means the program was given permission; it says nothing about
  how much. Least privilege means giving it only the access it needs, which here is reading the
  email addresses. Permission to change and delete everything on the drive is far more than that,
  so this breaks least privilege.
- **credit:** full for naming that the program has much more access than its job needs (it only
  needs to read addresses), so this is not least privilege, and that being authorized doesn't make
  it so. Half for "it has too much access" with nothing on why being authorized doesn't settle it,
  or for "authorized isn't the same thing" with nothing on how much access the program needs. None
  for a different quibble alone, such as that the newsletter should be sent by hand.
- **tutor note:** a learner who agrees, since the program was given its permissions properly, is
  reading least privilege as permission granted the right way; ask what the program would need if
  it only sent the newsletter.
