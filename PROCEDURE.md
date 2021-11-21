# PROCEDURE

## Abstract

**PROCEDURE** is a set of queries that can include inputs, loops, internal variables, etc. Some different features from **FUNCTION** is that **PROCEDURE** doesn't have to return the value. 

---

### e.g) Procedure to print out repeated star given INT n

```mysql
# make Delimiter $$, (default ;)
DELIMITER $$
# Drop procedure of same name if already exists
DROP PROCEDURE IF EXISTS print_stars$$
# Create procedure with print_stars(Any), with the input
CREATE PROCEDURE print_stars(IN n INT)
BEGIN
    # Declare variables that will be used inside the procedure
    DECLARE cnt INT;
    DECLARE star VARCHAR(2);
    # Set default value of the variables
    SET cnt = 1;
    SET star = '* ';
    # Loop to print out designated number of stars
    WHILE (cnt <= n) DO
        SELECT REPEAT(star, cnt);
        SET cnt = cnt + 1;
    END WHILE;
END$$
# make Delimiter ;, (was $$)
DELIMITER ;
# Call procedure
CALL print_stars(20);
```

---

### Conventions

- **Delimiter $$**
  - Queries inside the procedure is separated by delimiter ;
  - To separate out queries outside the procedure from queries inside. 