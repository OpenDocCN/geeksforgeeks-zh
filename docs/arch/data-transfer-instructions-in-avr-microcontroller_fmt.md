# AVR 微控制器中的数据传输指令

> 原文：[https://www.geeksforgeeks.org/data-transfer-instructions-in-avr-microcontroller/](https://www.geeksforgeeks.org/data-transfer-instructions-in-avr-microcontroller/)

[数据传输指令](https://www.geeksforgeeks.org/data-transfer-instructions-8085-microprocessor/)是将数据传输到[微控制器](https://www.geeksforgeeks.org/introduction-to-8051-microcontroller/)的指令。

这些指令可用于从以下位置传输数据：

## 寄存器到寄存器
在寄存器到寄存器的传输中，数据从一个寄存器传输到另一个寄存器。考虑一个必须执行二进制加法的例子。

**示例–**
在本例中，第一个数据将传输到 `B` 寄存器，然后从 `B` 寄存器传输到累加器寄存器。

```
MVI B, 05
MOV A, B
```

## 寄存器到内存
在此数据传输中，数据将从寄存器传输到给定的内存位置。考虑一个例子，其中给定的位置是 `201k`，您必须从累加器中复制数据。

**示例–**

```
STA 201K
```

## 内存到寄存器
在本次数据传输中，数据将从内存传输到寄存器。考虑一个例子，其中给定的位置是 `201k`，您必须将数据从这个内存位置加载到累加器中。

**示例–**

```
LDA 2020k
```

## 常量到寄存器
在此数据传输中，数据将被传输到立即给定的寄存器。考虑一个例子，其中给定的数据是 `05`，您必须将数据加载到累加器中。

**示例 –**

```
MVI A, 05
```

下表显示了不同的转移指令：

| 指令 | 操作数 | 说明 | 例子 |
| :--- | :--- | :--- | :--- |
| `MOV` | `d, s` | `d = s` | `MOV d, s` |
| `LDS` | `d, K` (内存位置) | `d = K` 处的值 | `LDS d, K` |
| `LD` | `d, s` | `d =` 存储在 `s` 存储单元中的值 | `LD d, s` |
| `LDI` | `d, K` (常数) | `d = K` | `LDI d, K` |
| `LPM` | `d, Z` (闪存) | 将寄存器 `Z` 中的值从闪存存储到存储在 `d` 寄存器中的存储位置 | `LPM d, z` |
| `IN` | `d, A` | 将值存储在 `d` 中的寄存器 `A` 中，其中 `A` 来自 `[0, 63]` (64 个输入/输出寄存器) | `IN d, A` |
| `OUT` | `A, d` | 将寄存器 `d` 中的值存储在 `A` 中，其中 `A` 来自 `[0, 63]` (64 个输入/输出寄存器) | `OUT A, d` |
| `STS` | `K, s` | 将寄存器 `s` 中的值存储到存储单元 `K` 中 | `STS K, s` |
| `ST` | `d, s` | 将寄存器 `s` 中的值存储到存储在 `d` 寄存器中的存储位置 | `ST d, s` |
| `PUSH` | `d` | 将 `d` 的内容推到堆栈的顶部 | `PUSH d` |
| `POP` | `d` | 从堆栈中移除最上面的条目，并将该值转移到 `d` | `POP d` |

`d` 和 `s` 是寄存器。`PUSH` 和 `POP` 指令严格用于维护堆栈。