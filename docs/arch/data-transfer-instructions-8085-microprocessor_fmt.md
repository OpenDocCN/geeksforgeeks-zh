# 8085 微处理器中的数据传输指令

> 原文: [https://www.geeksforgeeks.org/data-transfer-instructions-8085-microprocessor/](https://www.geeksforgeeks.org/data-transfer-instructions-8085-microprocessor/)

数据传输指令是在微处理器中传输数据的指令。它们也被称为复制指令。

## 指令列表

以下是显示逻辑指令列表的表格：

<figure class="table">

| 操作码 | 操作数 | 说明 | 例子 |
| --- | --- | --- | --- |
| `MOV` | `Rd`, `Rs` | `Rd = Rs` | `MOV A, B` |
| `MOV` | `Rd`, `M` | `Rd = M` | `MOV A, 2050H` |
| `MOV` | `M`, `Rs` | `M = Rs` | `MOV 2050H, A` |
| `MVI` | `Rd`, 8位数据 | `Rd = 8位数据` | `MVI A, 50H` |
| `MVI` | `M`, 8位数据 | `M = 8位数据` | `MVI 2050H, 50H` |
| `LDA` | 16位地址 | `A = 地址中的内容` | `LDA 2050H` |
| `STA` | 16位地址 | `地址 = A的内容` | `STA 2050H` |
| `LHLD` | 16位地址 | 直接载入高电平和低电平寄存器 | `LHLD 2050H` |
| `SHLD` | 16位地址 | 直接从高电平寄存器存储 | `SHLD 2050H` |
| `LXI` | `r.p.`, 16位数据 | 用数据加载指定的寄存器对 | `LXI H, 3050H` |
| `LDAX` | `r.p.` | 蓄电池上的间接负载 | `LDAX H` |
| `STAX` | `r.p.` | 从累加器 `A` 间接存储 | `STAX H` |
| `XCHG` | 无 | 用 `D` 交换 `H`，用 `E` 交换 `L` | `XCHG` |
| `PUSH` | `r.p.` | 将 `r.p.` 推入堆栈 | `PUSH H` |
| `POP` | `r.p.` | 将堆栈弹出到 `r.p.` | `POP H` |
| `IN` | 8位端口地址 | 将指定端口的内容输入到 `A` | `IN 15H` |
| `OUT` | 8位端口地址 | 将 `A` 的内容输出到指定的端口 | `OUT 15H` |

</figure>

## 符号说明

在表中，
`R` 代表寄存器
`M` 代表内存
`r.p.` 代表寄存器对