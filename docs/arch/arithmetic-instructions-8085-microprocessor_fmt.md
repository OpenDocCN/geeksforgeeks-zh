# 8085 微处理器中的算术指令

> 原文: [https://www.geeksforgeeks.org/arithmetic-instructions-8085-microprocessor/](https://www.geeksforgeeks.org/arithmetic-instructions-8085-microprocessor/)

算术指令是执行基本算术运算的指令，如加法、减法等。在 8085 微处理器中，目标操作数通常是累加器。

下表显示了算术指令列表：

| 操作码 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| `ADD` | `R` | `A = A + R` | `ADD B` |
| `ADD` | `M` | `A = A + M` | `ADD 2050` |
| `ADI` | `8位数据` | `A = A + 8位数据` | `ADI 50` |
| `ADC` | `R` | `A = A + R + prev. carry` | `ADC B` |
| `ADC` | `M` | `A = A + M + prev. carry` | `ADC 2050` |
| `ACI` | `8位数据` | `A = A + 8位数据 + prev. carry` | `ACI 50` |
| `SUB` | `R` | `A = A - R` | `SUB B` |
| `SUB` | `M` | `A = A - M` | `SUB 2050` |
| `SUI` | `8位数据` | `A = A - 8位数据` | `SUI 50` |
| `SBB` | `R` | `A = A - R - prev. carry` | `SBB B` |
| `SBB` | `M` | `A = A - M - prev. carry` | `SBB 2050` |
| `SBI` | `8位数据` | `A = A - 8位数据 - prev. carry` | `SBI 50` |
| `INR` | `R` | `R = R + 1` | `INR B` |
| `INR` | `M` | `M = M + 1` | `INR 2050` |
| `INX` | `rp` | `rp = rp + 1` | `INX H` |
| `DCR` | `R` | `R = R - 1` | `DCR B` |
| `DCR` | `M` | `M = M - 1` | `DCR 2050` |
| `DCX` | `rp` | `rp = rp - 1` | `DCX H` |
| `DAD` | `rp` | `HL = HL + rp` | `DAD H` |

## 表格说明
在表中：
- `R` 代表寄存器
- `M` 代表内存
- `M` 代表内存内容
- `rp` 代表寄存器对