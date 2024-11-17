# Command Prompt Examples for PostgreSQL
---

[SOURCE](https://raw.githubusercontent.com/PacktPublishing/Learn-PostgreSQL/refs/heads/master/README.md)

---
### Command prompts

In the book code listings and examples, the command prompts are one of the two that follows:
- a `$` stands for an Unix shell prompt (like Bourne, Bash, Zsh);
- a `forumdb=>` stands for the `psql(1)` command prompt when an active connection to the database is opened.

As an example, the following is a command issued on the operating system:

```shell
$ sudo service postgresql restart
```

while the following is a query issued within an active database connection:

```sql
forumdb=> SELECT CURRENT_TIMESTAMP;
```

### Administrative/Superusers command prompts

Whenere there is the need to execute a command or a statement with administrative privileges, the command prompt will reflect it using a `#` sign as the end part of the command prompt. For example, the following is an SQL statement issued as PostgreSQL administrator:

```sql
forumdb=# SELECT pg_terminate_backend( 987 );
```

ùPlease note the presence of the `#` in the `forumdb=#` prompt, as opposed to the `>` sign in the normal user `forumdb=>` prompt.

In the case a command on the operating system must be run with superuser (`root`) privileges, the command will be run via `sudo(1)`, as in:

```sql
$ sudo initdb -D /postgres/12
```

and therefore in this case the command prompt will not change, rather the presence of the `sudo(1)` command indicates `root` privileges are required.

## Creating the example database

The book is built over an example database that implements an *online forum* storage. In order to be able to execute any example of any chapter, the reader has to initialize the forum database.

The scripts in the folder `setup`, executed in lexicographically order, implement the example database and setup the environment so that other examples can be run against the database.

In particular, in order to get the database structure as shown in Chapter 4 and the followings, you have to executed something has follows:

```shell
psql -U <your-username> -h <database-host> < setup/00-forum-database.sql
```

where
- `your-username` is a PostgreSQL username of choice;
- `database-host` is the host the database is running on, if different from `localhost`.

The end result will be to have the `forumdb` created and populated with tables.
You can also invoke the script interactively from within a `psql` connection, such as:

```shell
psql -U <your-username> -h <database-host> template1

template1=> \i setup/-00-forum-database.sql
```

The simplest form to get the example database up and running is the following one (assuming you are running PostgreSQL locally):

```shell
$ psql -U postgres   template1 -c 'CREATE ROLE forumdb_user WITH LOGIN CREATEDB;'
$ psql -U forum_user template1 < setup/00-forum-database.sql
```
