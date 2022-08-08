---
id: b8izudgrbrv52qpq9oqnu1v
title: ACID
desc: ''
updated: 1650087013269
created: 1650086558852
---

- To ensure a database is consistent before and after work is done to it, databases uses atomic transactions, and actions like commits and rollbacks to handle failures appropriately. Transactions are, in other words, ACID.

## ACID
- Atomicity - entire transaction happens at once or does not happen at all - all or nothing /commit or abort
- Consistency - integrity constraints must be maintained so db is consistent before and after transaction
- Isolation - multiple transactions can occur concurrently w/o leading to inconsistency of db state
- Durability - ensures once transaction completes execution, updates and mods to db are stored and written to disk and persist in spite of system failure



