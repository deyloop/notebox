# SQL CROSS JOIN vs Multiple tables in FROM clause in SELECT

The following are functionally equivalent:

```sql
SELECT * 
FROM table1, table2
```
```sql
SELECT * 
FROM table1
CROSS JOIN table2
```

Both perform a cross join, cartesian product.

The second format using the explicit `JOIN` syntax has been the prefered
way of doing a cross join since a long time now.

---

Reference:

* Stack Overflow <https://stackoverflow.com/questions/53583412/what-is-the-difference-between-cross-join-and-multiple-tables-in-one-from>

---

    #convention #code
