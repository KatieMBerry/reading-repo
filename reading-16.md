## SQL Transactions
#### https://www.postgresqltutorial.com/postgresql-transaction/
- transaction = a unit of work of one or more operations
- must ensure ACID:
  - atomic: guarantees transaction completed
  - consistent: valid changes to data
  - isolated: transaction integrity is visible to other transactions
  - durable: changes to data are committed and stored in db
1. BEGIN TRANSACTION; BEGIN WORK; BEGIN - to precede INSERT statement
1. INSERT
1. COMMIT WORK; COMMIT TRANSACTION; COMMIT - to see the changes in data from the transaction/insert to table
  - now durable if system crashes
OR
1. ROLLBACK WORK; ROLLBACK TRANSACTION; ROLLBACK - to undo transaction

## Node-Postgres
#### https://node-postgres.com/features/transactions
- must use the same client instance for all statements within a transaction
- PostgresSQL isolates a transaction to individual clients
- DONT USE pool.query
