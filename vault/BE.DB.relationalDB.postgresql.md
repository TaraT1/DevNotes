---
id: kvbukaww7qbs3q8a90iap1e
title: postgresql
desc: ''
updated: 1689198005578
created: 1650504467626
---
Link SQLAlchemy within flask app  
db = SQLAlchemy(app)  
	- links db instance  
Need to connect to db by setting config var on flask app. Set on dictionary:  
app.config['SQLALCHEMY_DATABASE_URI'] = ' '  

## Postgres Install & Detail Notes

- The default host machine that runs your postgres server, on your machine, is localhost (aka, 127.0.0.1)
- The default port traditionally used to host your server is port 5432. There are very few reasons to use a different port than 5432.

Default connection settings are:

| Field    | Default Value          |
| -------- | ---------------------- |
| Host     | localhost or 127.0.0.1 |
| Port     | 5432                   |
| Username | postgres               |
| Password | (left blank)           |

## References

https://sp.postgresqltutorial.com/wp-content/uploads/2018/03/PostgreSQL-Cheat-Sheet.pdf

https://www.compose.com/articles/using-postgresql-through-sqlalchemy/

https://www.postgresqltutorial.com/psql-commands

[[BE.DB.relationalDB.postgresql.psql]]
