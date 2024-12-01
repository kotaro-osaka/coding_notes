# SQL
___
**Distinct**
```sql
-- Returns unique values (Filters out all duplicate values)
SELECT DISTINCT tools
FROM inventory;
```

**Null**
```sql
IS NULL
IS NOT NULL
```

**Between**
```sql
SELECT *
FROM movies
WHERE year BETWEEN 1990 AND 1999;
-- or
WHERE name BETWEEN 'A' AND 'C'; -- goes up to second value (only selects 'C')
```

**Order By**
```sql
-- Sort result by particular column
SELECT *
FROM movies
ORDER BY name DESC; -- ASC is default
```

**Limit**
```sql
-- Limits shown rows to a given maximum
SELECT *
FROM movies
LIMIT 10;
```

**Case**
```sql
SELECT name,
	CASE
		WHEN imdb_rating > 8 THEN 'Fantastic'
		WHEN imdb_rating > 6 THEN 'Poorly Received'
		ELSE 'Avoid at All Costs'
	END AS 'Review' -- If not added, will display conditions as heading
FROM movies;
```

**Aggregate Functions**
```sql
COUNT() -- Number of rows
SUM() -- Sum of values in column
MAX() MIN() -- Largest/Smallest value
AVG() -- Average of valies in column
ROUND() -- Round values in column
```

**Group By**
```sql
SELECT year,
   AVG(imdb_rating)
FROM movies
GROUP BY year
ORDER BY year;

-- Comes after WHERE and before ORDER BY or LIMIT
```

**Column Reference Numbers**
```sql
-- Column reference numbers
SELECT ROUND(imdb_rating),
   COUNT(name)
FROM movies
GROUP BY 1
ORDER BY 1;
```

**Having**
```sql
SELECT year,
   genre,
   COUNT(name)
FROM movies
GROUP BY 1, 2
HAVING COUNT(name) > 10;
```

