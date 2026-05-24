# SIC/XE 中使用的指令集

> 原文: [https://www.geeksforgeeks.org/instruction-set-used-in-sic-xe/](https://www.geeksforgeeks.org/instruction-set-used-in-sic-xe/)

## 先决条件与概述

先决条件 – [在简化教学计算机(SIC)中使用的指令集](https://www.geeksforgeeks.org/instruction-set-used-in-simplified-instructional-computer-sic/)。由于 SIC/XE 相对于 SIC 是向上兼容的，因此 SIC 中的所有指令也在 SIC/XE 中使用。SIC/XE 独有的指令有：

### 指令表

| 记忆码 | 操作数 | 操作码 | 说明 |
| :--- | :--- | :--- | :--- |
| `ADD` | `M` | `18` | `A = A + M` |
| `ADDF` | `M` | `58` | `F = F + M` |
| `ADDR` | `R2`,`R1` | `90` | `R2 = R2 + R1` |
| `AND` | `M` | `40` | `A = A & M` |
| `CLEAR` | `R1` | `04` | `R1 = 0` |
| `COMP` | `M` | `28` | 比较 `A` 和 `M` |
| `COMPF` | `M` | `88` | 比较 `F` 和 `M` |
| `COMPR` | `R2`,`R1` | `A0` | 比较 `R1` 和 `R2` |
| `DIV` | `M` | `24` | `A = A / M` |
| `DIVF` | `M` | `64` | `F = F / M` |
| `DIVR` | `R2`,`R1` | `9C` | `R2 = R2 / R1` |
| `FIX` | - | `C4` | `A = F (转换为整数)` |
| `FLOAT` | - | `C0` | `F = A (转换为浮点数)` |
| `HIO` | - | `F4` | 停止I/O通道 |
| `J` | `M` | `3C` | 跳转到 `M` |
| `JEQ` | `M` | `30` | 若 `SW` 等于则跳转到 `M` |
| `JGT` | `M` | `34` | 若 `SW` 大于则跳转到 `M` |
| `JLT` | `M` | `38` | 若 `SW` 小于则跳转到 `M` |
| `JSUB` | `M` | `48` | 跳转到子程序 `M` |
| `LDA` | `M` | `00` | `A = M` |
| `LDB` | `M` | `68` | `B = M` |
| `LDCH` | `M` | `50` | `A (最右字节) = M` |
| `LDF` | `M` | `70` | `F = M` |
| `LDL` | `M` | `08` | `L = M` |
| `LDS` | `M` | `6C` | `S = M` |
| `LDT` | `M` | `74` | `T = M` |
| `LDX` | `M` | `04` | `X = M` |
| `LPS` | `M` | `D0` | 从 `M` 加载处理器状态 |
| `MUL` | `M` | `20` | `A = A * M` |
| `MULF` | `M` | `60` | `F = F * M` |
| `MULR` | `R2`,`R1` | `98` | `R2 = R2 * R1` |
| `NORM` | - | `C8` | `F` 规格化 |
| `OR` | `M` | `44` | `A = A \| M` |
| `RD` | `M` | `D8` | 从设备 `M` 读取 |
| `RMO` | `R2`,`R1` | `AC` | `R2 = R1` |
| `RSUB` | - | `4C` | 从子程序返回 |
| `SHIFTL` | `R1`,`n` | `A4` | 左移 `R1` `n` 次 |
| `SHIFTR` | `R1`,`n` | `A8` | 右移 `R1` `n` 次 |
| `SIO` | - | `F0` | 启动I/O通道 |
| `SSK` | `M` | `EC` | 设置 `M` 的保护键 |
| `STA` | `M` | `0C` | `M = A` |
| `STB` | `M` | `78` | `M = B` |
| `STCH` | `M` | `54` | `M = A (最右字节)` |
| `STF` | `M` | `80` | `M = F` |
| `STI` | `M` | `D4` | 中断使能时存储 `M` |
| `STL` | `M` | `14` | `M = L` |
| `STS` | `M` | `7C` | `M = S` |
| `STT` | `M` | `84` | `M = T` |
| `STX` | `M` | `10` | `M = X` |
| `SUB` | `M` | `1C` | `A = A - M` |
| `SUBF` | `M` | `5C` | `F = F - M` |
| `SUBR` | `R2`,`R1` | `94` | `R2 = R2 - R1` |
| `SVC` | `n` | `B0` | 产生服务调用 |
| `TD` | `M` | `E0` | 测试设备 `M` 是否就绪 |
| `TIO` | - | `F8` | 测试I/O通道是否就绪 |
| `TIX` | `M` | `2C` | `X = X+1`；比较 `X` 和 `M` |
| `TIXR` | `R1` | `B8` | `X = X+1`；比较 `X` 和 `R1` |
| `WD` | `M` | `DC` | 写入设备 `M` |

### 符号说明

这里，
- `M` 代表内存地址。
- `R1` 和 `R2` 是寄存器 (`A`, `B`, `S`, `T`, `X`, `L`, `PC`, `SW`)。