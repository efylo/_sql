# SELECT

## Abstract

**SELECT** is the most fundamental query of SQL. Some specific grammars would differ by a language, and here denotes the MySQL. 

---

## Assumption (a table TB)

| ROW \ COL | A     | B     | C    |
| --------- | ----- | ----- | ---- |
| 0         | 'abc' | 'bcd' | 0    |
| 1         | 'ace' | 'bar' | 0    |
| 2         | 'aaa' | 'bbb' | 0    |
| 3         | 'are' | 'but' | 0    |
| 4         | 'Amy' | 'Ben' | 1    |
| 5         | 'aim' | 'ban' | 0    |
| 6         | 'AOS' | 'BTS' | 2    |
| 7         | 'avi' | 'bmp' | 0    |
| 8         | 'API' | 'BFS' | 2    |
| 9         | 'Ayo' | 'Bye' | 1    |

---

## Grammars

### Fundamental

```mysql
SELECT * FROM TB;
-- Return all rows of all columns of table
SELECT A FROM TB;
-- Return all rows of a column A
SELECT DISTINCT A FROM TB;
-- Return all rows of a distinct column A (duplication removed)
SELECT A FROM TB 
WHERE A = 'abc';
-- Return row of a column A if A is 'abc'
SELECT A FROM TB 
WHERE A LIKE 'a%';
-- Return row of a column A if A starts with 'a'
```

---

### Group

```mysql
SELECT A, COUNT(A) FROM TB
GROUP BY A;
-- COUNT number of columns that have the same A values
SELECT A, COUNT(A) FROM TB
GROUP BY A
HAVING A LIKE 'A%';
-- COUNT number of columns that have the same A values that starts with 'A'
SELECT A, COUNT(A) FROM TB
WHERE A LIKE 'a%'
GROUP BY A
HAVING A LIKE '%e';
-- COUNT number of columns starting with 'a' (WHERE first)
-- that have the same A values ending with 'e' (HAVING then)
```



---

### Sort

```mysql
SELECT A FROM TB
ORDER BY A;
-- Returns a column of A with ascending order (in default, ASC)
SELECT A FROM TB
ORDER BY A DESC;
-- Returns a column of A with descending order (from 'z' to 'a')
```

---

### Limit

```mysql
SELECT A FROM TB
LIMIT 5;
-- Returns 5 column starting from first row
SELECT A FROM TB
LIMIT 3, 5;
-- Returns 5 column starting from fourth row (fourth = index of 3)
```

---

### IF

```mysql
SELECT IF(A LIKE 'A%', 'A', 'a')
FROM TB;
-- IF A starts with 'A', returns 'A'. ELSE, returns 'a'. 
-- So, input = (condition, return value when condition TRUE, when FALSE)
```

---

### Multiple Queries

```mysql
SELECT A FROM TB;
SELECT B FROM TB;
-- Queries are separated by DELIMITER, which is semi-colon(;) in default.
```

---

### Print

```mysql
SELECT 'Hello, SQL';
-- Even without table, can print some value
```

---

### Group Concat

GROUP_CONCAT(column_name) prints out all columns of a group, separated by (,). 

```mysql
SELECT
  CONCAT('GROUP ', C, ': '), 
  CONCAT(GROUP_CONCAT(A), ' / ', GROUP_CONCAT(B))
FROM TB
GROUP BY C;
-- GROUP 0: abc, ace, aaa, are, aim, avi / bcd, bar, bbb, but, ban, bmp
-- GROUP 1: Amy / Ben
-- GROUP 2: AOS, API / BTS, BFS
```

---

### Variable

**@** makes the use of variable inside **SELECT** possible. 

```mysql
SELECT
  (CASE @Vc WHEN T1.C1 THEN @Vid := @Vid + 1 ELSE @Vid := 1) AS ID1, 
  T1.A AS A1,
  T1.B AS B1,
  (@Vc := T1.C) AS C1
FROM
  TB AS T1,
  (SELECT @Vid := 0, @Vc := -1) AS V
ORDER BY
  C
-- Makes the ID via certain group
-- ID's can be then used to pivot the table via c
```

