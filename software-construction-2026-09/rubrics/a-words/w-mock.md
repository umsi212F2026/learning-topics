# Rubric: mock

### q-define-mock

- **type:** free
- **goal:** w-mock
- **move:** DEFINE
- **answer:** a stand-in that a test puts in the place of something real the code would otherwise
  use, usually the database or an outside service. The code under test talks to the stand-in
  instead of the real thing, and the test can then check what the code asked the stand-in to do.
  Nothing is really stored, sent or deleted.
- **credit:** full credit for "a stand-in for something real, usually the database or a service,
  that a test puts in its place". No credit for "a stub", "a fake", "a test double" or "something
  that pretends" alone, with no sense of what it stands in for. No credit for "sample data put into the database for the test", which is
  a test dataset, or for a mock-up of what the app will look like.

### q-mock-vs-test-data

- **type:** free
- **goal:** w-mock
- **move:** DISTINGUISH
- **answer:** the three notes are real content in a real database, and the code under test uses the
  database exactly as it normally would. A mock is not content at all: it is a stand-in put in the
  database's place, so the real database is never involved. With the test data, the test can check
  what actually ended up stored; with the mock, it can only check what the code asked the stand-in
  to do.
- **credit:** full credit for the difference that matters: test data is real content and the real
  database is still being used, while a mock replaces the database itself. The consequence version
  is also full credit: with a mock nothing is really stored, so the test can only check the request
  that was made. Half credit for "one is data and one is code" with nothing about whether the real
  database is used. No credit for a difference only of size or speed, and no credit for describing
  a mock as a database full of made-up notes.

### q-mock-earns-no-assertions

- **type:** free
- **goal:** w-mock
- **move:** INTERPRET
- **answer:** it tells you the saving code asked its stand-in to store the note, so the app is
  making the request it should. It leaves open everything after that: whether the real database
  accepted it, whether it was kept where a reload would find it, whether it was kept at all. If
  saving were broken at the database, the stand-in would still be asked and this test would still
  pass, so the answer does not settle your question.
- **credit:** full credit for both halves: the test shows the request was made to the stand-in, and
  it shows nothing about the real database keeping the note. Half credit for either half alone. No
  credit for taking the answer as showing that saving works, and no credit for reading "test
  double" as a second test, a duplicate note, or a backup database.
