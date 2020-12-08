## PostgreSQL Join:
- Combines columns from one or more tables based on values of common columns (self join = Primary keys & foreign keys)
  - inner join joins on common values of table a and table b
  - https://www.postgresqltutorial.com/postgresql-joins/ for left, right, full outer, cross, natural join descriptions
  
## One to One Data Model:
- one element of set/row of table A only linked to one element of set/row of table B and visa versa
  - mother to child analogy

## One to Many:
- an element/row of table A may be linked to many elements/rows of table B, but a member/row of table B is linked to only one element/row of table A
  - book to pages analogy
  
## Many to Many:
- Table A may contain a parent instance for which there are many children in table B and vice versa
  - A = authors and B = books analogy
  - implemented by associated/join table
  - HasAndBelongsTo Many relationship
