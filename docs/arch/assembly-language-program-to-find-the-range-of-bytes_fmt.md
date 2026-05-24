# 汇编语言程序查找字节范围

> 原文: [https://www.geeksforgeeks.org/assembly-language-program-to-find-the-range-of-bytes/](https://www.geeksforgeeks.org/assembly-language-program-to-find-the-range-of-bytes/)

## 问题
编写一个汇编语言程序，如果输入数字 `BYTE1` 位于 `50H` 到 `80H` 之间，则在输出端口 `PORT2` 上显示。如果 `BYTE1` 小于 `50H`，则只需在输出端口 `PORT1` 上打印 `00H`。

## 示例
```
Input:  64H
Output: output at PORT2 -->64H
Input:  40H
Output: output at PORT1 -->00H 
```

## 算法
1.  将字节 `BYTE1` 装入累加器 `A`。
2.  将累加器中的数据复制到寄存器 `B`。
3.  从累加器中减去 `50H`。
4.  减法为负数时跳转。
5.  如果跳转条件为真，那么它将简单地在端口 `PORT1` 打印 `00H`。
6.  如果跳转条件为假，则字节 `BYTE1` 将大于 `50H`，在进一步的指令中，它还将检查字节 `BYTE1` 的上限 `80H`，因此所有的数字都位于 `50H` 到 `80H` 之间，这些数字将在端口 `PORT2` 打印。

## 程序
| 存储地址 | 记忆术 | 评论 |
| --- | --- | --- |
| 2000 | `MVI A, BYTE1` | `A` <- `BYTE1` |
| 2002 | `MOV B, A` | `B` <- `A` |
| 2003 | `SUI 50H` | `A` <- `A - 50H` |
| 2005 | `JC DELETE` | 跳转到 `DELETE`，如果 `CY = 1` |
| 2007 | `MOV A, B` | `A` <- `B` |
| 2008 | `SUI 80H` | `A` <- `A - 80H` |
| 200A | `JC DISPLAY` | 跳转到 `DISPLAY`，如果 `CY = 1` |
| 200C | `DELETE: XRA A` | `A` <- `A XOR A` |
| 200D | `OUT PORT1` | 在 `PORT1` 输出累加器的内容 |
| 200F | `HLT` | 程序终止 |
| 2010 | `DISPLAY: MOV A, B` | `A` <- `B` |
| 2011 | `OUT PORT2` | 在 `PORT2` 输出累加器的内容 |
| 2013 | `HLT` | 程序终止 |

## 解释
1.  `MVI A, BYTE1`: 从 `BYTE1` 加载累加器 `A`。
2.  `MOV B, A`: 将累加器的内容复制到寄存器 `B`。
3.  `SUI 50H`: 从累加器的内容中减去 `50H` (`BYTE1`) 并将其载入累加器。
4.  `JC DELETE`: 这里 `JC` 是带进位标志检查条件的跳转指令，如果减法为负，进位标志为 `1`，如果减法为正，则进位标志为 `0`。如果累加器内容 (`BYTE1`) 大于或等于 `50H`，`SUI 50H` 将为正。如果 `CY=0`，则结果为正，不会执行跳转。
5.  `MOV A, B`: 将寄存器 `B` (`BYTE1`) 的内容复制到累加器。
6.  `SUI 80H`: 从累加器中减去 `80H`。如果累加器的内容少于 `80H`，那么结果将是正的，如果数字在 `50H` 到 `7FH` 的范围内，它将跳转到 `DISPLAY` 标签并在端口 `PORT2` 显示字节。
7.  如果在步骤4中，`JC DELETE` 为真表示减法结果为正，那么它将跳转到 `DELETE` 并清除累加器的内容，并在输出端口 `PORT1` 显示 `00H`。