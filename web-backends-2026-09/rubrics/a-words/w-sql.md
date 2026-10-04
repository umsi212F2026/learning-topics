# Rubric: SQL

### q-sql-vs-database

- **type:** free
- **goal:** w-sql
- **move:** DISTINGUISH
- **answer:** the database is the thing that holds the books, a store on your laptop with tables in
  it. SQL is the language it is asked things in: give me every book, add this row, change this one.
  The database is what is asked, and SQL is how you ask it; a different database could be asked in
  the same language.
- **credit:** full credit for the difference that matters: the database is the store, and SQL is the
  language the questions and changes are written in. Half credit for "SQL is used with databases"
  with nothing about its being a language for asking. Do not accept "SQL is a kind of database",
  which is the confusion itself, since SQLite and Postgres are databases and SQL is what they are
  asked in. Do not accept "SQL is the data".

### q-sql-never-typed

- **type:** free
- **goal:** w-sql
- **move:** CATCH
- **answer:** whether they typed it is beside the point. If the app keeps its data in a SQL database,
  then something in the server is asking that database in SQL every time data is saved or read
  back, whether the agent wrote those queries out or a library wrote them. Their app uses SQL; they
  have just never seen it.
- **credit:** full credit for saying the SQL is being sent by the server, written by the agent or by
  a library, whether or not the learner typed any, so the app does use it. Half credit for "the agent
  wrote the SQL for you" with nothing about its running whenever the app saves or reads. Do not
  accept a different quibble as the error: that they ought to learn SQL, that JavaScript and SQL are
  both languages, or that some databases are not asked in SQL, which is true and is not what this
  sentence gets wrong.

### q-sql-sqlite-one-file

- **type:** mcq
- **goal:** w-sql
- **move:** INTERPRET
- **answer:** 3
- **credit:** 1 swaps the two: SQLite is the database and SQL is the language it is asked in. 2 puts
  the data somewhere else, when the message says it is a file on your own laptop. 4 has the page
  reaching the database itself, when the message says the server is what asks it.
