# DATA TYPES

## Abstract

Before heading on to MySQL, I should firstly get familiar to the data types. 

There are 5 data types referring to MySQL docs. 

1. Numeric
2. Date and Time
3. String
4. Spatial
5. The JSON

---

## 1. Numeric Data Types

### 1-1. Integer Types

They are used to represent integer data, represented as **<u>INT</u>**. 

Different from floating-point types, **<u>INT</u>** is the exact numeric value. 

**<u>INT(M)</u>** determines the precision, it only displays M digits, and aligned right. 

There are 5 different integer types, which are displayed below. 

| Type      | Storage(Bytes) |
| --------- | -------------- |
| TINYINT   | 1              |
| SMALLINT  | 2              |
| MEDIUMINT | 3              |
| INT       | 4              |
| BIGINT    | 8              |

### 1-2. Fixed-Point Types

Not used in general programming languages, they are used to assign the exact numeric value with fixed number of digits. 

**<u>DEC</u>**, which stands for Decimal, is the type used to represent fixed-point types. 

**<u>DEC(M, D)</u>** means there are M number of digits(자릿수) with D decimal places(소수점 자릿수). 

On default, D is equal to 0. 

e.g)

> ```mysql
> height DEC(5, 2)
> # height can exist from -999.99 to 999.99
> # where the difference of heights is multiple of 0.01
> ```

### 1-3. Floating-Point Types

Different from fixed-point, floating-point represents approximate numeric data values. Since it's approximateness, there can be errors even though your formula is correct. 

e.g)

> ```python
> print((10/3 == 10/2 + 10/1))
> # False even though the formula is True. 
> ```

**<u>FLOAT</u>** is used to represent 4-byte floating-point types, **<u>DOUBLE</u>** to represent 8-byte. 

**<u>FLOAT(*p*)</u>** or **<u>DOUBLE(*p*)</u>** are used to determine the precision of the data type. Though, the precision only determines the storage size. 

**<u>FLOAT(M, D)</u>** or **<u>DOUBLE(M, D)</u>** are permitted in MySQL, with M as the number of digits and D as the decimal places. 

### 1-4. Bit-Value Types

**<u>BIT</u>** is used to store bit values. **<u>BIT(M)</u>** stands for M-bit values. 

Bit value is specified through b'*value*', where *value* is the combination of zeros and ones. 

---

## Date and Time Data Types



---

## Reference

- [MySQL 8.0 Reference Manual :: 11 Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)