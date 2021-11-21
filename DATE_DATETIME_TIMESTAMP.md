# DATE, DATETIME, TIMESTAMP

## Abstract

DATE, DATETIME, TIMESTAMP is used to represent the date and time data. They are formatted as below table, constrained upon the range. Also, MySQL supports microseconds precision for DATETIME and TIMESTAMP. 

|               | FORMAT                | FROM                  | TO                    |
| ------------- | --------------------- | --------------------- | --------------------- |
| **DATETIME**  | 'YYYY-MM-DD hh:mm:ss' | '1000-01-01 00:00:00' | '9999-12-31 23:59:59' |
| **TIMESTAMP** | 'YYYY-MM-DD hh:mm:ss' | '1970-01-01 00:00:01' | '2038-01-19 03:14:07' |
| **DATE**      | 'YYYY-MM-DD'          | '1000-01-01'          | '9999-12-31'          |

---

## Functions

There are numerous functions supporting DATE and TIME data types. Extraction of the year, month, or maybe the hour can be easily done through built-in functions. 

|               | IN                 | DESCRIPTION                    |
| ------------- | ------------------ | ------------------------------ |
| CONVERT_TZ()  | dt, from_tz, to_tz | Converts time zone of datetime |
| CURDATE()     | -                  | Returns the current date       |
| DATE_FORMAT() | date, format       | Formats the date value         |
| HOUR()        | time               | Returns the hour               |

And much more exist. 

---

## Reference

- [MySQL :: MySQL 8.0 Reference Manual / Functions and Operators / Date and Time Functions](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)
- [MySQL :: MySQL 8.0 Reference Manual / The DATE, DATETIME, and TIMESTAMP Types](https://dev.mysql.com/doc/refman/8.0/en/datetime.html)