# CREATE TABLE

## Abstract

Since database using SQL deals with the table things, creating a table is one of the most fundamental process of SQL. Though, you first have to create a database before creating a table. 

---

### e.g) Creating a table of people

```mysql
CREATE TABLE `people`
(
    `id` INT PRIMARY KEY,
    `phone` INT,
    `age` INT,
    `country` VARCHAR(20),
    `height` FLOAT,
    `weight` FLOAT
);
```

