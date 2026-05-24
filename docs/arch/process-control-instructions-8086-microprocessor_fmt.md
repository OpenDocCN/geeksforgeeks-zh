# 8086 微处理器中的过程控制指令

> 原文：[https://www.geeksforgeeks.org/process-control-instructions-8086-microprocessor/](https://www.geeksforgeeks.org/process-control-instructions-8086-microprocessor/)

过程控制指令是通过设置(1)或重置(0)标志寄存器的值来控制处理器动作的指令。

下表显示了过程控制说明的列表：

| 操作码 | 操作数 | 说明 | 示例 |
| :--- | :--- | :--- | :--- |
| `STC` | none | 将进位标志设置为 1 | `STC` |
| `CLC` | none | 将进位标志重置为 0 | `CLC` |
| `CMC` | none | 对进位标志取反 | `CMC` |
| `STD` | none | 将方向标志设置为 1 | `STD` |
| `CLD` | none | 将方向标志重置为 0 | `CLD` |
| `STI` | none | 将中断标志设置为 1 | `STI` |
| `CLI` | none | 将中断标志重置为 0 | `CLI` |