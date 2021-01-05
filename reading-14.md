## Postgres Joins Between Tables 
#### https://www.postgresql.org/docs/current/tutorial-join.html; 
#### https://www.postgresqltutorial.com/postgresql-joins/

- if there are duplicate column names in the two tables you'd need to qualify the column names to show which one you meant, as in:
```javaScript
SELECT weather.city, weather.temp_lo, weather.temp_hi,
       weather.prcp, weather.date, cities.location
    FROM weather, cities
    WHERE cities.name = weather.city; 
 ``` 
- can avoid this using JOIN
```javaScript
SELECT *
    FROM weather INNER JOIN cities ON (weather.city = cities.name);
```

- LEFT/RIGHT OUTER JOIN:
  - the table mentioned on the left/right of the join operator will have each of its rows in the output at least once, where the table on the right/left
  will only have those rows output that match some row of the left/right table
       
- SELF JOIN: comparing data against other data in same table
  - use aliases to reference column data to compare
 ```javaScript
SELECT W1.city, W1.temp_lo AS low, W1.temp_hi AS high,
    W2.city, W2.temp_lo AS low, W2.temp_hi AS high
    FROM weather W1, weather W2
    WHERE W1.temp_lo < W2.temp_lo
    AND W1.temp_hi > W2.temp_hi;

     city      | low | high |     city      | low | high
---------------+-----+------+---------------+-----+------
 San Francisco |  43 |   57 | San Francisco |  46 |   50
 Hayward       |  37 |   54 | San Francisco |  46 |   50
``` 
- FULL OUTER JOIN: returns a result set that contains all rows from both left and right tables, with the matching rows from both sides if available
  - if no match, the columns of the table will be filled with NULL
