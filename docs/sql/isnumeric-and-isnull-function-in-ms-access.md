# MS Access 中的 IsNumeric()和 IsNull()函数

> 原文:[https://www . geesforgeks . org/is numeric-and-is null-function in-ms-access/](https://www.geeksforgeeks.org/isnumeric-and-isnull-function-in-ms-access/)

**1。IsNumeric()函数:**
**MS Access 中的 IsNumeric** ()函数用于检查一个表达式是否可以被求值为数字。它返回 TRUE (-1)表示表达式可以被识别为数字；否则，它返回 False(0)。

**语法**:

```sql
IsNumeric(expression)
```

**参数–**必选；一个表情。
**表达式–**它是包含数值表达式或字符串表达式的任何变体。
**返回–**如果整个表达式被识别为数字，则返回 True(-1)，否则返回 False(0)。

*   **Example-1 :**

    ```sql
    SELECT IsNumeric("GeeksforGeeks");
    ```

    **输出–**

    ```sql
    0
    ```

*   **Example-2 :**

    ```sql
    SELECT IsNumeric(111);
    ```

    **输出–**

    ```sql
    -1
    ```

    **注意:**如果表达式是日期表达式，IsNumeric 返回 False。

*   **Example-3 :**

    ```sql
    SELECT IsNumeric(#11/09/2020#);
    ```

    **输出–**

    ```sql
    0
    ```

**2。IsNull()函数:**
MS Access 中的 IsNull()函数用于检查表达式是否为空值。它返回真(-1)表示表达式是空值，而假(0)表示表达式不是空值。

**语法**:

```sql
IsNull (expression)
```

**参数–**必选；一个表情。
**表达式–**它是包含数值表达式或字符串表达式的任何变体。
**返回–**如果表达式为空，则返回真(-1)，否则返回假(0)。

*   **Example-1 :**

    ```sql
    SELECT IsNull("GeeksforGeeks");
    ```

    **输出–**

    ```sql
    0
    ```

*   **Example-2 :**

    ```sql
    SELECT IsNull(11);
    ```

    **输出–**

    ```sql
    0
    ```

*   **Example-3 :**

    ```sql
    SELECT IsNull(null);
    ```

    **输出–**

    ```sql
    -1
    ```