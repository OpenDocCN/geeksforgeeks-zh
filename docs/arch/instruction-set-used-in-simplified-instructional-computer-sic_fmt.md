# 简化教学计算机中使用的指令集

> 原文：[https://www.geeksforgeeks.org/instruction-set-used-in-simplified-instructional-computer-sic/](https://www.geeksforgeeks.org/instruction-set-used-in-simplified-instructional-computer-sic/)

先决条件 – [简化教学计算机(SIC)](https://www.geeksforgeeks.org/simplified-instructional-computer-sic/)

这些是编程简化教学计算机(SIC)时使用的指令。

这里
`A` 代表累加器
`M` 代表内存
`CC` 代表条件码
`PC` 代表程序计数器
`R` 代表最右字节
`L` 代表联动寄存器

| 记忆的 | 操作数 | 操作码 | 说明 |
| --- | --- | --- | --- |
| `ADD` | `M` | `18` | `A = A + M` |
| `AND` | `M` | `40` | `A = A AND M` |
| `COMP` | `M` | `28` | 比较 `A` 和 `M` |
| `DIV` | `M` | `24` | `A = A / M` |
| `J` | `M` | `3C` | `PC = M` |
| `JEQ` | `M` | `30` | 如果 `CC` 设置为=，`PC = M` |
| `JGT` | `M` | `34` | 如果 `CC` 设置为>，`PC = M` |
| `JLT` | `M` | `38` | 如果 `CC` 设置为<，`PC = M` |
| `JSUB` | `M` | `48` | `L = PC`，`PC = M` |
| `LDA` | `M` | `00` | `A = M` |
| `LDCH` | `M` | `50` | `A[R] = M[R]` |
| `LDL` | `M` | `08` | `L = M` |
| `LDX` | `M` | `04` | `X = M` |
| `MUL` | `M` | `20` | `A = A * M` |
| `OR` | `M` | `44` | `A = A OR M` |
| `RD` | `M` | `D8` | `A[R] = M[R]` 指定的数据 |
| `RSUB` | | `4C` | `PC = L` |
| `STA` | `M` | `0C` | `M = A` |
| `STCH` | `M` | `54` | `M[R] = A[R]` |
| `STL` | `M` | `14` | `M = L` |
| `STSW` | `M` | `E8` | `M = SW` |
| `STX` | `M` | `10` | `M = X` |
| `SUB` | `M` | `1C` | `A = A – M` |
| `TD` | `M` | `E0` | `M` 指定的测试设备 |
| `TIX` | `M` | `2C` | `X = X+1`；比较 `X` 和 `M` |
| `WD` | `M` | `DC` | `M[R] = A[R]` 指定的设备 |