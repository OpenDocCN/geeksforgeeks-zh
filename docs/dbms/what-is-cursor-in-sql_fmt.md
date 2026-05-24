# 什么是 SQL 中的游标？

> 原文：[https://www.geeksforgeeks.org/what-is-cursor-in-sql/](https://www.geeksforgeeks.org/what-is-cursor-in-sql/)

**光标**是临时存储器或临时工作站。它由数据库服务器在用户对表执行 `DML`（数据操作语言）操作时分配。游标用于存储数据库表。游标有两种类型：隐式游标和显式游标。这些解释如下。

## 隐式游标

隐式游标也称为 `SQL SERVER` 的默认游标。当用户执行 `DML` 操作时，这些游标由 `SQL SERVER` 分配。

## 显式光标

显式光标由用户在需要时创建。显式游标用于以逐行方式从表中获取数据。

### 如何创建显式光标

1.  **声明光标对象。**
    **语法：** `DECLARE cursor_name CURSOR FOR select_statement`

    ```sql
    DECLARE s1 CURSOR FOR SELECT * FROM studDetails
    ```

2.  **打开光标连接。**
    **语法：** `OPEN cursor_name`

    ```sql
    OPEN s1
    ```

3.  **从光标处获取数据。**
    共有 6 种方法可以从光标处访问数据。它们如下：
    *   `FIRST` 用于仅从游标表中获取第一行。
    *   `LAST` 用于仅从游标表中获取最后一行。
    *   `NEXT` 用于从游标表中正向取数据。
    *   `PRIOR` 用于从游标表中向后取数据。
    *   `ABSOLUTE n` 用于从光标表中获取精确的第 `n` 行。
    *   `RELATIVE n` 用于以递增方式和递减方式获取数据。
    **语法：** `FETCH NEXT|FIRST|LAST|PRIOR|ABSOLUTE n|RELATIVE n FROM cursor_name`

    ```sql
    FETCH FIRST FROM s1
    FETCH LAST FROM s1
    FETCH NEXT FROM s1
    FETCH PRIOR FROM s1
    FETCH ABSOLUTE 7 FROM s1
    FETCH RELATIVE -2 FROM s1
    ```

4.  **关闭光标连接。**
    **语法：** `CLOSE cursor_name`

    ```sql
    CLOSE s1
    ```

5.  **释放光标内存。**
    **语法：** `DEALLOCATE cursor_name`

    ```sql
    DEALLOCATE s1
    ```