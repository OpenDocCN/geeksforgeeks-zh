# MySQL 中的循环

> 原文:[https://www.geeksforgeeks.org/loops-in-mysql/](https://www.geeksforgeeks.org/loops-in-mysql/)

**MySQL LOOP** 语句可以用来运行一段代码或一组语句，一次又一次，这取决于条件。

**语法:**

```sql
[labelname:] LOOP
   statements
END LOOP [labelname]
```

**参数–**

*   [T0】 label name: 【T1] Both the beginning and the end are optional labels.
*   **Statements:** They can have one or more statements, each with a semicolon (; ) and executed by the LOOP.

带有 LEAVE 语句的 LOOP 语句的语法:

```sql
[labelname]: LOOP
     -- terminate the loop
   IF condition THEN
       LEAVE [labelname];
   END IF;
END LOOP;
```

**示例-1 :**

```sql
DROP PROCEDURE IF EXISTS GeekLoop();
```

```sql
DELIMITER $ 
CREATE PROCEDURE GeekLoop()
 BEGIN
DECLARE no INT;
  SET no = 0;
  loop: LOOP
    SET no = no +1;
    select no ;
    IF no =5 THEN
     LEAVE loop;
    END IF;
 END LOOP loop;
SELECT no;
END $
DELIMITER ;
```

检查输出的语句:

```sql
CALL GeekLoop();
```

**输出–**

```sql
0, 1, 2, 3, 4, 5
```

**示例-2 :**

```sql
DELIMITER $
CREATE FUNCTION Geekdemo (value1 INT)
RETURNS INT
BEGIN
 DECLARE value2 INT;
 SET value2 = 0;
 label: LOOP
  SET income = value2 + value1 ;
  IF value2 < 4000 THEN
    ITERATE label;
  END IF;
  LEAVE label;
 END LOOP label;
 RETURN value2 ;
END $
DELIMITER ;
```

检查输出的查询:

```sql
CALL Geekdemo();
```

**输入–**

```sql
value1: 3500
```

**输出–**

```sql
value2: 3500
```

**例-3 :**

```sql
CREATE TABLE Geektable (value VARCHAR(50) NULL DEFAULT NULL); 
```

```sql
DELIMITER $ 
CREATE PROCEDURE ADD()
 BEGIN
  DECLARE a INT Default 1 ;
  simple_loop: LOOP     
    insert into table1 values(a);
    SET a=a+1;
    IF a=11 THEN
      LEAVE simple_loop;
    END IF;
 END LOOP simple_loop;
END $
```

**查询检查输出–**

```sql
CALL ADD();
Select value 
from Geektable;
```

**输出–**

```sql
1
2
3
4
5
6
7
8
9
10 
```