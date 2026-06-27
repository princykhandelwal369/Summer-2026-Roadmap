# COMMON MISTAKES

- SQL and MySQL are not the same thing. SQL is a language while MySQL is a software. 
- CHAR is used only for fixed bytes, while VARCHAR is used for variable bytes.
- If an already existing database is created, it shows error- Database already exists
- Don't confuse NOT NULL with UNIQUE — NOT NULL just means "must have a value", UNIQUE means "no duplicates."
- While inserting, mismatching the number of values with the number of columns listed.
- While using order by, NULL values depends upon the software being used. It is considered smallest in MySQL but is placed at the end in PostgreSQL.
- Never run UPDATE/DELETE without WHERE unless you mean to affect the whole table. Test with SELECT first.
- DELETE vs TRUNCATE vs DROP are NOT interchangeable — know which one you actually need.
- WHERE cannot use aggregate functions (no "WHERE COUNT(*) > 5") — use HAVING instead.
- GROUP BY: every selected column must be aggregated or in the GROUP BY list — non-strict MySQL may silently let this through with garbage results.
- LIKE '%word%' can't use an index — avoid on large tables / hot queries if possible.
- NOT IN with a NULL in the list returns zero rows unexpectedly — sanitize subqueries with NOT NULL or use NOT EXISTS instead.
- BETWEEN with datetime upper bounds can silently exclude same-day timestamps — use < next_day pattern.
- != / <> never matches NULL rows — must explicitly add OR col IS NULL if you want them included.
