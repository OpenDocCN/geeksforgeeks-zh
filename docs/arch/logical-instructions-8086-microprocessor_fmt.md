# 8086 微处理器中的逻辑指令

> 原文：[https://www.geeksforgeeks.org/logical-instructions-8086-microprocessor/](https://www.geeksforgeeks.org/logical-instructions-8086-microprocessor/)

逻辑指令是执行诸如“与”、“或”等基本逻辑操作的指令。在 8086 微处理器中，目标操作数不必是累加器。

下表显示了逻辑指令列表：

| 操作码 | 操作数 | 目的地 | 例子 |
| --- | --- | --- | --- |
| `AND` | `d, S` | `D = D AND S` | `AND AX, 0010` |
| `OR` | `d, S` | `D = D OR S` | `OR AX, BX` |
| `NOT` | `D` | `D = NOT D` | `NOT AL` |
| `XOR` | `d, S` | `D = D XOR S` | `XOR AL, BL` |
| `TEST` | `d, S` | 执行逐位“与”运算并影响标志寄存器 | `TEST [0250], 06` |
| `SHR` | `D, C` | 将 `D` 中的每个位向右移动 `C` 次，`0` 存储在 `MSB` 位置 | `SHR AL, 04` |
| `SHL` | `D, C` | 将 `D` 中的每个位向左移动 `C` 次，`0` 存储在 `LSB` 位置 | `SHL AX, BL` |
| `ROR` | `D, C` | 将 `D` 中的所有位向右旋转 `C` 次 | `ROR BL, CL` |
| `ROL` | `D, C` | 将 `D` 中的所有位向左旋转 `C` 次 | `ROL BX, 06` |
| `RCR` | `D, C` | 将 `D` 中的所有位与进位标志一起向右旋转 `C` 次 | `RCR BL, CL` |
| `RCL` | `D, C` | 将 `D` 中的所有位与进位标志一起向左旋转 `C` 次 | `RCL BX, 06` |

这里 `D` 代表目的地，`S` 代表来源，`C` 代表计数。它们可以是寄存器、数据或存储器地址。