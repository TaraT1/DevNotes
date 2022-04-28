---
id: 9qi7tfisp9myy5456xpbh2e
title: psql
desc: ''
updated: 1650506073730
created: 1650385204767
---
## POSTGRES, PSQL
- psql is an interactive terminal application for connecting and interacting with your local postgres server on your machine.
- Connect using $ psql <dbname>
- psql lets you
    - Directly type and execute SQL commands to your database
    - Inspect and preview your database and database tables using psql meta-commands

### Useful basic psql commands
psql <dbname> [<username>]
Starts psql with a connection to dbname. Optionally use another user than current user
In psql:
$ \l - List all databases on the server, their owners, and user access levels
$ \c <dbname> - Connect to a database named 
$ \dt - Show database tables 
$ \d <tablename> - Describe table schema
$ \q - Quit psql, return to the terminal
$ \? - Get help, see list of available commands

### Can use SQL commands
We can use string interpolation to compose a SQL query using python strings. Two methods for doing so include:
1. Using %s, passing in a tuple as the 2nd argument in cursor.execute() (~/fsudac/demo2.py)
2. Using named string parameters %(foo)s, passing in a dictionary instead. (demo3.py)
3. set dictionary to data var, set template string SQL (demo3.py)

# Using postgres, psql
After your first install, and each time you restart your machine sre you will have to also restart the postgres service, or else you will get a Is the server running? error.
	1. To start the service, type sudo service postgresql start.
	2. To connect to postgres, type sudo -u postgres psql.
You should get a prompt asking for your password. If this doesn't work, then you can try the second option listed below.
	1. Switch users to postgres by typing su - postgres.\c
	2. Type psql.
When this is successful you will see the command line change to look like this 
```
$ postgres=#
```

\c postgres - connect to db named postgres 

\l - lists dbs

\d "Table_name"

``` psql
SELECT * FROM "Table_name";
```

### Sometimes necessary to reset db
- Start the PostgreSQL server

```
$ sudo service postgresql start
```

- Stop the PostgreSQL server:
``` 
$ sudo service postgresql stop
```

The default user is postgres
login as particular user:
```
$ sudo -u <username> -i 
```

create new db
```
$ createdb <db name>
```

destroy db
```
$ dropdb <db name>
```
reset db
```
$ dropdb <db name> && createdb <db name>
```
### postgres
Command	|Desc
------ | -----
sudo -u <username> -I	|login. Default uname is postgres
createdb <dbname> |	create
dropdb <dbname>	| destroy
dropdb <dbname> && createdb <dbname> |	Reset db

### psql 
Command	|Desc
------ | -----
psql <dbname> <username> |	starts psql w connection to dbname
\l (as in lucy)	| list dbs on server, owners, access levels
\c <dbname>	| connects to db named
\dt	| shows db tables
\d <"tablename">	| describes table schema, lists columns
\q	| quit psql, return to terminal

[[AnBE.DB.relationalDB.postgresql]]