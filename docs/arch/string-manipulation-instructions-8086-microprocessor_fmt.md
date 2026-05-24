# 8086 微处理器中的串操作指令

> 原文：[https://www.geeksforgeeks.org/string-manipulation-instructions-8086-microprocessor/](https://www.geeksforgeeks.org/string-manipulation-instructions-8086-microprocessor/)

字符串是内存中连续位置可用的一系列数据字节或字。它被称为字节串或字串。它们的内存总是按顺序分配的。用于操作字符串的指令称为字符串操作指令。

下表显示了字符串操作指令列表：

| 操作码 | 操作数 | 说明 | 例 |
| :--- | :--- | :--- | :--- |
| `REP` | 指令 | 重复给定指令直到 `CX` != 0 | `REP MOVSB` |
| `REPE` | 指令 | 重复给定指令而 `CX` = 0 | `REPE` |
| `REPZ` | 指令 | 重复给定指令而 `ZF` = 1 | `REPZ` |
| `REPNE` | 指令 | 重复给定指令而 `CX` != 0 | `REPNE` |
| `REPNZ` | 指令 | 重复给出的指令，而 `ZF` = 0 | `REPNZ` |
| `MOVSB` | 无 | 将 `DS:SI` 给出的字节内容移动到 `ES:DI` | `MOVSB` |
| `MOVSW` | 无 | 将 `DS:SI` 给出的字内容移动到 `ES:DI` | `MOVSW` |
| `MOVSD` | 无 | 将 `DS:SI` 给出的双字内容移动到 `ES:DI` | `MOVSD` |
| `LODSB` | 无 | 将地址 `DS:SI` 处的字节移入 `AL`；`SI` 增加/减少 1 | `LODSB` |
| `LODSW` | 无 | 将地址 `DS:SI` 处的字移入 `AX`；`SI` 增加/减少 2 | `LODSW` |
| `LODSD` | 无 | 将地址 `DS:SI` 处的双字移入 `EAX`；`SI` 增加/减少 4 | `LODSD` |
| `STOSB` | 无 | 将 `AL` 的内容移动到 `ES:DI` 给定的字节地址；`DI` 增加/减少 1 | `STOSB` |
| `STOSW` | 无 | 将 `AX` 的内容移动到 `ES:DI` 给定的字地址；`DI` 增加/减少 2 | `STOSW` |
| `STOSD` | 无 | 将 `EAX` 的内容移动到 `ES:DI` 给定的双字地址；`DI` 增加/减少 4 | `STOSD` |
| `SCASB` | 无 | 将 `ES:DI` 处的字节与 `AL` 进行比较，并根据结果设置标志 | `SCASB` |
| `SCASW` | 无 | 将 `ES:DI` 处的字与 `AX` 进行比较，并根据结果设置标志 | `SCASW` |
| `SCASD` | 无 | 将 `ES:DI` 处的双字与 `EAX` 进行比较，并根据结果设置标志 | `SCASD` |
| `CMPSB` | 无 | 将 `ES:DI` 处的字节与 `DS:SI` 处的字节进行比较，并设置标志 | `CMPSB` |
| `CMPSW` | 无 | 将 `ES:DI` 处的字与 `DS:SI` 处的字进行比较，并设置标志 | `CMPSW` |
| `CMPSD` | 无 | 将 `ES:DI` 处的双字与 `DS:SI` 处的双字进行比较，并设置标志 | `CMPSD` |