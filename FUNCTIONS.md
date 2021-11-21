# FUNCTIONS

## Abstract

Like other functions in programming language, functions in SQL do specific things to the attributes. 

| Name                  | Description                                   |
| --------------------- | --------------------------------------------- |
| COUNT(A)              | Counts the number of attribute A              |
| COUNT(DISTINCT A)     | Counts the number of distinct attribute A     |
| LENGTH(S)             | Returns the length of string S                |
| SUBSTR(S, P, L)       | Returns substring of S from P to P+L          |
| REPEAT(S, N)          | Returns the string that repeats S for N times |
| CONCAT(A, B, [C, ..]) | Returns the string A + B + C...               |

### Substring

- 3 inputs = string S, starting position P, length L
- The position P is the index that starts from 1. 
- e.g) if you want to get the last 3 words, **SUBSTR(S, LENGTH(S)-2, 3)** is right. 