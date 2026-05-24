# 8086 确定 n 个数字数组中的数字立方体的程序

> 原文：[https://www.geeksforgeeks.org/8086-program-to-determine-cubes-of-numbers-in-an-array-of-n-numbers/](https://www.geeksforgeeks.org/8086-program-to-determine-cubes-of-numbers-in-an-array-of-n-numbers/)

## 问题
在 8086 微处理器中编写一个程序，找出 8 位 n 个数的立方，其中大小“n”存储在偏移量 `500` 处，个数从偏移量 `501` 开始存储，并将结果数存储到偏移量 `501` 中。（假设立方体的长度限制为 8 位）。

## 示例
![](img/8259e4673dfacb2cceb9f8080c7e7045.png)

## 算法
1.  将 `500` 存储到 `SI`，并将偏移量 `500` 的数据加载到寄存器 `CL`，并将寄存器 `CH` 设置为 `00`（用于计数）。
2.  将 `SI` 值增加 1。
3.  从偏移 `SI` 到寄存器 `AL` 的加载编号（值）。
4.  将寄存器 `AL` 的值移到 `BL`。
5.  将寄存器 `AL` 中的值乘以自身。
6.  将寄存器 `AL` 中的值乘以 `BL`。
7.  将结果（寄存器 `AL` 的值）存储到存储器偏移 `SI`。
8.  将 `SI` 值增加 1。
9.  循环到 6 以上，直到 `CX` 寄存器为 0。

## 程序
| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| `400` | `MOV SI, 500` | `SI` |
| `403` | `MOV CL, [SI]` | `CL` |
| `405` | `MOV CH, 00` | `CH` |
| `407` | `INC SI` | `SI` |
| `408` | `MOV AL, [SI]` | `AL` |
| `40A` | `MOV BL, AL` | `BL` |
| `40C` | `MUL AL` | `AX=AL*AL` |
| `40E` | `MUL BL` | `AX=AL*BL` |
| `410` | `MOV [SI], AL` | `AL >[SI]` |
| `412` | `INC SI` | `SI` |
| `413` | `LOOP 408` | 跳到 `408` IF `CX`!=0，`CX=CX-1` |
| `415` | `HLT` | 结束 |

## 解释
1.  `MOV SI, 500`: 将 `SI` 的值设置为 `500`。
2.  `MOV CL, [SI]`: 从偏移 `SI` 向寄存器 `CL` 加载数据。
3.  `MOV CH, 00`: 将寄存器 `CH` 的值设置为 `00`。
4.  `INC SI`: `SI` 值增加 1。
5.  `MOV AL, [SI]`: 从偏移 `SI` 到寄存器 `AL` 的加载值。
6.  `MOV BL, AL`: 将寄存器 `AL` 的值移动到 `BL`。
7.  `MUL AL`: 寄存器 `AL` 的值乘以 `AL`。
8.  `MUL BL`: 寄存器 `AL` 的值乘以 `BL`。
9.  `MOV [SI], AL`: 存储偏移量 `SI` 处寄存器 `AL` 的值。
10. `INC SI`: `SI` 值增加 1。
11. `LOOP 408`: 如果 `CX` 不是 0，`CX=CX-1`，跳转到地址 `408`。
12. `HLT`: 停止。