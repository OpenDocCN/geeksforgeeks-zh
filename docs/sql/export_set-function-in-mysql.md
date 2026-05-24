# MySQL 中的 EXPORT_SET()函数

> 原文:[https://www.geeksforgeeks.org/export_set-function-in-mysql/](https://www.geeksforgeeks.org/export_set-function-in-mysql/)

**EXPORT_SET() :**
这个函数有助于返回一个字符串，该字符串将显示数字位。该函数需要 5 个参数才能运行。该函数将第一个参数(即整数)转换为二进制数字，如果二进制数字为 1，则返回“开”，如果二进制数字为 0，则返回“关”。

**语法:**

```sql
EXPORT_SET
(bits, on, off, separator, number of bits)
```

**参数:**
这个函数接受 5 个参数。

*   **位–**
    结果将被格式化的整数。
*   **on–**
    如果二进制数为 1，则返回。
*   **off–**
    如果二进制数为 0，则返回。
*   **分隔符–**
    将放在返回值之间的分隔符。
*   **位数–**
    结果将出现的位数

**返回:**
该函数将返回一个字符串，该字符串将显示数字位。

**示例-1:**
EXPORT _ SET()函数的一般工作原理。

```sql
SELECT EXPORT_SET(10, 'On', 'Off', ':', 5) 
AS Export;
```

**输出:**

| 出口 |
| 关闭:打开:关闭:打开:关闭 |

**示例 2 :**
通过更改 2 <sup>nd</sup> 和 3 <sup>rd</sup> 参数来运行 EXPORT_SET()函数。

*   **Using “Y” and “N” as second and third argument respectively –**

    ```sql
    SELECT EXPORT_SET(11, 'Y', 'N', ', ', 4) 
    AS Export;
    ```

    **输出:**

    | 出口 |
    | 是，是，不是，是 |

*   **Using “1” and “0” as second and third argument respectively –**

    ```sql
    SELECT EXPORT_SET(11, 1, 0, ', ', 4) 
    AS Export;
    ```

    **输出:**

    | 出口 |
    | 1, 1, 0, 1 |

**示例-3 :**
通过更改 4 <sup>第</sup>个参数来运行 EXPORT_SET()函数。

*   **Using “-” as the fourth argument –**

    ```sql
    SELECT EXPORT_SET(10, 1, 0, '-', 4) 
    AS Export;
    ```

    **输出:**

    | 出口 |
    | 0-1-0-1 |

*   **Using “::” as the fourth argument –**

    ```sql
    SELECT EXPORT_SET(10, 1, 0, '::', 4) 
    AS Export;
    ```

    **输出:**

    | 出口 |
    | 0::1::0::1 |

**示例-4 :**
通过更改第 5 个<sup>参数来运行 EXPORT_SET()函数。</sup>

*   **Using 10 as the fifth argument –**

    ```sql
    SELECT EXPORT_SET(9, 'Y', 'N', ' ', 10) 
    AS Export;
    ```

    **输出:**

    | 出口 |
    | 你好，你好 |

*   **Using 20 as the fifth argument –**

    ```sql
    SELECT EXPORT_SET(9, 1, 0, ' ', 20) 
    AS Export;
    ```

    **输出:**

    | 出口 |
    | 1 0 0 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 |