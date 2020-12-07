## Inside a Computer
- motherboard: main circuit board that contains:
  - CPU = central processing unit; "brain" of computer
  - RAM = random access memory for calculations (short term cleared upon shutdown; as RAM decreases so does performance)
  - Harddrives = solid state drivers; long-term storage for software, files, docs

## Postgres INSERT:
- inserts a new row into an existing table

INSERT into table_name (col1, col2)
  VALUES (1,2);
  
 => Returns "insert oid count" where oid is object identifier (uesd as primary key; default 0)
 - counts # of successfully inserted rows
 - can use asterik for all or specify value of row to return
    - can rename value returned "return as..."
 
 ## Postgres SELECT:
 - queries data from a single table
 
 SELECT
  select_list (column or list of columns)
 FROM
  table_name;
 
 => better practice to specify columns instead of * for performance
 - can use "||" to concat columns: first_name || ' ' || last_name
 
## Postgres UPDATE:
- updates existing table data

UPDATE table_name
SET (specify columns)
WHERE condition; - optional; if not specified, updates all

=> returns updated count of rows, including unchanged?

## Postgres DELETE:

DELETE FROM table_name
WHERE condition; - optional; if not specified, deletes all
- deletes one or more rows

=> returns deleted rows
- removes data but doesn't change table structure

