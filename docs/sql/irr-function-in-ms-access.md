# MS 接入中的 IRR()功能

> 原文:[https://www.geeksforgeeks.org/irr-function-in-ms-access/](https://www.geeksforgeeks.org/irr-function-in-ms-access/)

[MS Access](https://www.geeksforgeeks.org/difference-between-microsoft-excel-and-microsoft-access/) 中的 IRR()函数用于返回一个 Double 值，指定一系列周期性现金流的内部收益率，例如，付款和收款。

**语法:**

```sql
IRR( values () [, guess ] )
```

**参数:**
IRR()函数接受六个参数，如上所述，如下所述。

*   **values()–**
    它接受指定现金流值的 Double 数组。在内部收益率函数中，接受的数组必须至少包含一个负值(付款)和一个正值(收据)，这是必需的。
*   **猜测–**
    它接受一个变量，该变量指定用户估计将通过内部收益率返回的值。如果省略，猜测是 0.1(10%)。(可选)

**返回:**
以双精度返回，指定内部收益率。

**注:**
在 IRR 函数中解释付款和收款的顺序，它使用数组内值的顺序。付款和收款值应以正确的顺序输入。每个时期的现金流不必像年金那样固定。

**示例-1 :**
我们假设*猜测*价值(业务成本)等于 7500，连续四年的年收入存储在 values()中。
考虑这些值，如–

```sql
value(0) = 3000
value(1) = 5000
value(2) = 1200
value(3) = 4000

```

```sql
SELECT IRRInterest = IRR( values(), -7500)*100 AS Interest_IRR;

```

**输出:**

| **利息 _ 内部收益率** |
| Twenty-eight |

**例-2 :**
现金流数据在表 test_tbl 中提供。

| **ID** | **现金流** |
| one | Fifty thousand two hundred and forty-three point two five |
| Two | Fifty thousand two hundred and forty-three point two five |
| three | Fifty thousand two hundred and forty-three point two five |
| four | Fifty thousand two hundred and forty-three point two five |
| five | Fifty thousand two hundred and forty-three point two five |
| six | Fifty thousand two hundred and forty-three point two five |

```sql
SELECT IRR(cursor( SELECT cash_flow FROM test_tbl order by id asc )) as Interest

```

**输出:**

| 利息 |
| .490408759 |