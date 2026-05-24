# AVR 微控制器中的逻辑指令

> 原文：[https://www.geeksforgeeks.org/logical-instructions-in-avr-microcontroller/](https://www.geeksforgeeks.org/logical-instructions-in-avr-microcontroller/)

逻辑指令是执行基本算术运算的指令，如与、或、异或等。在 AVR 微控制器中，目标操作数总是一个寄存器。

## 逻辑指令表

| 指令 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| `AND` | `d`, `s` | `D = D AND s`<br>对操作数执行与运算，并将结果存储在左侧操作数中 | `AND D, S` |
| `ANDI` | `d`, `k` (常数) | `D = D AND k`<br>对操作数执行 AND 运算，并将结果存储在左手操作数中，右手操作数为常数 | `ANDI D, k` |
| `OR` | `d`, `s` | `D = D OR s`<br>对操作数执行或运算，并将结果存储在左侧操作数中 | `OR D, S` |
| `ORI` | `d`, `k` | `D = D OR k`<br>对操作数执行 OR 运算，并将结果存储在左手操作数中，右手操作数为常数 | `ORI D, k` |
| `EOR` | `d`, `s` | `D = D XOR s`<br>对操作数执行异或运算，并将结果存储在左手操作数中 | `EOR D, S` |
| `COM` | `d` | `D = 1's complement of D`<br>补码动作将“1”变为“0”，将“0”变为“1” | `COM D` |
| `NEG` | `d` | `D = 2's complement of D`<br>该指令取二进制补码 | `NEG D` |
| `CP` | `d`, `s` | 比较 `D` 和 `S`<br>这个指令真的是一个减法动作。唯一的区别是寄存器的值不变 | `CP D, S` |
| `CPI` | `d`, `k` | 比较 `D` 和 `k`<br>`CP` 和 `CPI` 的唯一区别是 `CPI` 有一个操作数作为常数 | `CPI D, k` |

## 注

`D` 和 `S` 分别为目的地和来源。两者都是寄存器。`k` 是一个常数。