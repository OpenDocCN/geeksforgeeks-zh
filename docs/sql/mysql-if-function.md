# MySQL | IF()函数

> 原文:[https://www.geeksforgeeks.org/mysql-if-function/](https://www.geeksforgeeks.org/mysql-if-function/)

MySQL **IF()** 函数用于验证条件。如果条件为真，IF()函数返回一个值，如果条件为假，则返回另一个值。函数的返回值可以是数字或字符串，具体取决于函数的使用环境。
IF()函数接受一个参数，该参数是要评估的条件。

**语法:**

```sql
IF(condition, true_value, false_value)
```

**使用的参数:**

*   **条件–**用于指定要评估的条件。
*   **true _ value–**这是一个可选参数，用于指定条件评估为真时要返回的值。
*   **false _ value–**这是一个可选参数，用于指定条件评估为 false 时要返回的值。

**返回值:**
如果条件为真，MySQL IF()函数返回一个值，如果条件为假，则返回不同的值。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例-1:** 在数值条件下实现 IF()函数并返回字符串值。

```sql
SELECT IF(5<12, 'TRUE', 'FALSE'); 
```

**输出:**

```sql
TRUE 
```

**示例-2:** 实现 IF()函数比较两个字符串。

```sql
SELECT IF(STRCMP('geeksforgeeks', 'gfg')=0, 'TRUE', 'FALSE'); 
```

**输出:**

```sql
FALSE 
```

**示例-3:** 在数值条件下实现 IF()函数并返回数值。

```sql
SELECT IF(5<12, '1', '0'); 
```

**输出:**

```sql
1 
```