# 在 SQL 中打印不同的星形图案

> 原文:[https://www . geesforgeks . org/print-different-star-patterns-SQL/](https://www.geeksforgeeks.org/print-different-star-patterns-sql/)

让我们看看如何使用 SQL 打印各种类型的模式。

**语法:**

```sql

Declare @variable_name DATATYPE     -- first declare all the
                                    -- variables with datatype
                                    -- like (int)

select @variable = WITH_ANY_VALUE   -- select the variable and 
                                    -- initialize with value

while CONDITION                     -- condition like @variable > 0 

begin                               -- begin

print replicate('*', @variable)     -- replicate insert the *
                                    -- character in variable times

set increment/decrement             -- in increment/decrement
                                    -- @variable= @variable+1
END                                 -- end while loop

```

**First Pattern :**

```sql
DECLARE @var int               -- Declare
SELECT @var = 5                -- Initialization
WHILE @var > 0                 -- condition
BEGIN                          -- Begin
PRINT replicate('* ', @var)    -- Print
SET @var = @var - 1            -- decrement
END                            -- END
```

输出:

```sql
* * * * *
* * * * 
* * * 
* * 
*

```

**第二种模式:**

```sql
DECLARE @var int                  -- Declare 
SELECT @var = 1                   -- initialization 
WHILE @var <= 5                   -- Condition
BEGIN                             -- Begin
PRINT replicate('* ', @var)       -- Print
SET @var = @var + 1               -- Set
END                               -- end
```

输出:

```sql
*
* *
* * *
* * * *
* * * * *

```

**第三种模式:**

```sql
DECLARE @var int, @x int                 -- declare two variable
SELECT @var = 4,@x = 1                   -- initialization
WHILE @x <=5                             -- condition
BEGIN
PRINT space(@var) + replicate('*', @x)   -- here space for 
                                         -- create spaces 
SET @var = @var - 1                      -- set
set @x = @x + 1                          -- set
END                                      -- End
```

输出:

```sql
    *
   **
  ***
 ****
*****

```

**第四种模式:**

```sql
DECLARE @var int, @x int                 -- declare two variable
SELECT @var = 0,@x = 5                   -- initialization
WHILE @x > 0                             -- condition
BEGIN
PRINT space(@var) + replicate('*', @x)   -- here space for
                                         -- create spaces 
SET @var = @var + 1                      -- set
set @x = @x - 1                          -- set
END                                      -- End
```

输出:

```sql
*****
 ****
  ***
   **
    *

```