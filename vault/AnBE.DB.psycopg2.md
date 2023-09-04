---
id: b1cixd8vgpsw3eyqgc9we1q
title: psycopg2
desc: ''
updated: 1650508425404
created: 1650384706982
---

# Basic usage of psycopg2 

reference: https://www.psycopg.org/docs/usage.html

???psycopg and psql
- Psycopg can have graphical interface I believe

DBAPI provides std interface for programming lang to talk to relational db server; aka db adaptor
-psycopg2 - py

### Example code
```
import psycopg2
conn = psycopg2.connect('dbname=todoapp_development user=amy')
cursor = conn.cursor()
```
### Open a cursor to perform database operations
```
cur = conn.cursor()
```
### drop any existing todos table
```
cur.execute("DROP TABLE IF EXISTS todos;")
```

### (re)create the todos table
- (note: triple quotes allow multiline text in python)
```
cur.execute("""
  CREATE TABLE todos (
    id serial PRIMARY KEY,
    description VARCHAR NOT NULL
  );
""")
```
## commit, so it does the executions on the db and persists in the db
```
conn.commit()
cur.close()
conn.close()
```

## Fetching results
We can use string interpolation to compose a SQL query using python strings. Two methods for doing so include:
	1. Using %s, passing in a tuple as the 2nd argument in cursor.execute()
	2. Using named string parameters %(foo)s, passing in a dictionary instead.

Additional Resources
	- psycopg2 docs: Basic module usage (http://initd.org/psycopg/docs/usage.html)

From bash 5.7.20:
'''
tarat@TaraT-ClevoCru:~$ python3.7 -m pip install psycopg2
Defaulting to user installation because normal site-packages is not writeable
Requirement already satisfied: psycopg2 in /usr/lib/python3/dist-packages (2.8.5)
'''

apt-get vs. pip
https://askubuntu.com/questions/431780/apt-get-install-vs-pip-install

Using pip in global context is plain wrong and must not be used, because it will mess up system python installation. pip and apt-get a completely different things, and it is wrong to compare them. Try to install a python module which depends on other non-python libraries and you will quickly realise why you might need apt-get. – mestia Jan 11 '19 at 7:43 

From <https://askubuntu.com/questions/431780/apt-get-install-vs-pip-install> 

5.8.20
used apt-get to install.