# 使用多路复用器的 1 位全加器

> 原文：[https://www.geeksforgeeks.org/1-bit-full-adder-using-multiplexer/](https://www.geeksforgeeks.org/1-bit-full-adder-using-multiplexer/)

## 先决条件
[多路复用器](https://www.geeksforgeeks.org/multiplexers-in-digital-logic/) | [全加器](https://www.geeksforgeeks.org/full-adder-in-digital-logic/)

## 简介
[多路复用器](https://www.geeksforgeeks.org/multiplexers-in-digital-logic/)和[全加器](https://www.geeksforgeeks.org/full-adder-in-digital-logic/)是两种不同的数字逻辑电路。多路复用器是一个数字开关。它允许来自多个来源的数字信息被路由到一条输出线上。另一方面，全加器电路执行三位相加，并产生和与进位作为输出。我们的目标是使用多路复用器而不是通常的基本逻辑门来构建全加器电路。

## 步骤 1
要使用 `MUX` 实现全加器，我们需要首先创建全加器的真值表。

### 全加器真值表

| 输入 | | | 输出 | |
| :---: | :---: | :---: | :---: | :---: |
| **A** | **B** | **C-In** | **Sum** | **Carry** |
| Zero | Zero | Zero | Zero | Zero |
| Zero | Zero | one | one | Zero |
| Zero | one | Zero | one | Zero |
| Zero | one | one | Zero | one |
| one | Zero | Zero | one | Zero |
| one | Zero | one | Zero | one |
| one | one | Zero | Zero | one |
| one | one | one | one | one |

## 步骤 2
我们需要从真值表中找出求和 (`Sum`) 与进位 (`Carry`) 输出的最小项。

```
For Sum -     f(A, B, C-In) = Σ(1,2,4,7)
For Carry -   f(A, B, C-In) = Σ(3,5,6,7)
```

## 步骤 3
现在我们需要求和 (`Sum`) 和进位 (`Carry`) 的等式。为了找到答案，我们将创建求和与进位输出的设计表。

> **注意:** 为了理解下一部分，建议通过 [**使用多路复用器实现 SOP 功能**](https://www.geeksforgeeks.org/implementation-of-sop-function-using-multiplexer/)。

### 总和 (`Sum`) 设计表

![](img/419102d3ec5f65a1e21c57a5af52fb19.png)

对于求和最小项 (1，2，4，7)，输出为高，因此在设计表中用圆圈标出。
*   对于 `D0`，只有 4 为高，对应于表中的 `A`，因此多路复用器 (`M0`) 的 `D0` 输入将为 `A`。
*   其他输入也遵循同样的规则：`D1 = A'`，`D2 = A'`，`D3 = A`。

### 进位 (`Carry`) 输出设计表

![](img/b71273b798fb5d043b38ea61115a8d7b.png)

对于进位最小项 (3，5，6，7)，输出为高，因此它们在设计表中被圈起来，就像 `Sum` 的设计表一样。
*   这里，对于 `D0`，输入 0 和 4，两者都为低，因此多路复用器的输入将为 `0`。
*   对于 `D3`，3 和 7 都为高电平，因此多路复用器的输入为 `1`。
*   `D1` 和 `D2` 将沿用之前的规则，为 `D1 = A` 和 `D2 = A`。

现在，我们已经将所有输入信息输入到多路复用器，因此我们可以设计逻辑电路。

## 逻辑电路

![](img/148efc12dcb20959bb3edee41330aeb1.png)

### 说明

**输入：**
*   `M0` 多路复用器的输入按照 `SUM` 的设计表，即 `D0 = A`，`D1 = A'`，`D2 = A'`，`D3 = A`。
*   `M1` 多路复用器的输入按照 `CARRY` 的设计表，即 `D0 = 0`，`D1 = A`，`D2 = A`，`D3 = 1`。
*   `M0` 和 `M1` 的选择线均与 `B` & `Cin` 输入相连。

**输出：**
*   `M0` 多路复用器的输出将具有 `SUM` 作为输出。
*   `M1` 多路复用器将具有 `CARRY` 作为输出。

## 应用
这个电路是全加器电路，所以会有全加器电路的所有应用。以下列表：
1.  片上库的基本构件。
2.  在处理器和其他类型的计算设备中，算术逻辑单元使用加法器。