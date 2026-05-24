# 马里亚数据库中的 LCASE 功能、左功能和定位功能

> 原文:[https://www . geesforgeks . org/lcase-function-left-function-locate-function-in-mariadb/](https://www.geeksforgeeks.org/lcase-function-left-function-and-locate-function-in-mariadb/)

**1。LCASE 函数:**
在马里亚数据库中，LCASE 函数用于将所有字符串转换为小写。该函数将字符串 is 作为参数，并以小写字符串形式返回该字符串。如果字符串可以包含任何不包含字母的字符，那么这将不受此函数的影响。它的工作原理类似于 LOWER()函数。该函数将使用当前的字符映射集转换字符。默认情况下是 latin1。

**语法:**

```sql
LCASE(string) 
```

**参数:**

*   **字符串–**将以小写形式转换的字符串。

**Return :**
它返回所有小写字符的字符串。

**示例-1 :**

```sql
SELECT LCASE('Geeksforgeeks');

```

**输出:**

```sql
geeksforgeeks

```

**示例-2 :**

```sql
SELECT LCASE('CO_MPU_TER');

```

**输出:**

```sql
co_mpu_ter
```

**示例-3 :**

```sql
SELECT LCASE('@ Self @paced');
```

**输出:**

```sql
@ self @paced
```

**2。左函数:**
在马里亚数据库中，左函数用于从给定的总长度的左边提取字符串。这个函数将字符串 is 作为一个参数，它将返回该字符串从左到右的字符数。如果给定的数字超过了字符串的长度，那么它将返回原始字符串。

**语法:**

```sql
LEFT(string, number_of_characters)
```

**参数:**

*   **字符串–**左字符需要查找的字符串。
*   **字符数–从字符串开始的字符总数。**

**Return :**
它返回字符串左边的字符数。

**示例-1 :**

```sql
SELECT LEFT('data', 1);
```

**输出:**

```sql
d
```

**示例-2 :**

```sql
SELECT LEFT('Article', 5);
```

**输出:**

```sql
Artic
```

**示例-3 :**

```sql
SELECT LEFT('dsa', 108);
```

**输出:**

```sql
dsa
```

**3。定位函数:**
在马里亚数据库中，定位函数用于查找字符串中子串的第一个位置。这个函数将把 substring is 作为第一个参数，而第二个参数将是 string，第三个参数将是起点。它将从开始位置返回字符串中第一个出现子字符串的位置。如果子字符串不在字符串中，那么它将返回 0。它适用于不区分大小写的操作。

**语法:**

```sql
LOCATE( substring, string, [start_position ] )
```

**参数:**

*   **子串–**将在给定字符串中搜索的子串。*   **字符串–**将在其中执行子字符串搜索的字符串。*   **Start_position –** Starting position of the string from which substring will be searched.

    **返回:**
    它将返回字符串中子字符串的第一个位置。

    **示例-1 :**

    ```sql
    SELECT LOCATE('n', 'noncase');
    ```

    **输出:**

    ```sql
    1
    ```

    **示例-2 :**

    ```sql
    SELECT LOCATE('n', 'banana', 4);
    ```

    **输出:**

    ```sql
    5
    ```

    **示例-3 :**

    ```sql
    SELECT LOCATE('new', 'Example');
    ```

    **输出:**

    ```sql
    0
    ```