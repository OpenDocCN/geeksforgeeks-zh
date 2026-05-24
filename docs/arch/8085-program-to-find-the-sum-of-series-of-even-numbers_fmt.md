# 8085 程序求偶数系列的和

> 原文: [https://www.geeksforgeeks.org/8085-program-to-find-the-sum-of-series-of-even-numbers/](https://www.geeksforgeeks.org/8085-program-to-find-the-sum-of-series-of-even-numbers/)

## 问题
从给定的数字列表中计算一系列偶数的和。列表的长度在存储单元 `2200H` 中，系列从存储单元 `2201H` 开始。结果将存储在存储位置 `2210H`。

## 示例
```
Input : 
2200H= 4H
2201H= 20H
2202H= l5H
2203H= l3H
2204H= 22H

Output : 
Result 2210H = 42H
```

## 程序
| 记忆术 | 操作数 | 评论 |
| --- | --- | --- |
| `LDA` | `2200H` | [一] |
| `MOV` | `C, A` | 初始化计数器 |
| `MVI` | `B, 00H` | 总和= 0 |
| `LXI` | `H, 2201H` | 初始化指针 |
| `BACK:` | `MOV A, M` | 拿到号码 |
| `ANI` | `0lH` | 屏蔽位 1 至位 7 |
| `JNZ` | `SKIP` | 如果数字是奇数，不要加 |
| `MOV` | `A, B` | 得到总数 |
| `ADD` | `M` | 总和=总和+数据 |
| `MOV` | `B, A` | 将结果存储在 B 寄存器中 |
| `SKIP:` | `INX H` | 增量指针 |
| `DCR` | `C` | 减量计数器 |
| `JNZ` | `BACK` | 如果计数器 0 重复 |
| `MOV` | `A, B` | 将结果存储在寄存器中 |
| `STA` | `2210H` | 存储总和 |
| `HLT` |  | 终止程序执行 |

## 解释
微处理器是一种计算机处理器，将中央处理器的功能集成在单个集成电路上。

1.  `A` 是一个 8 位累加器，用于直接加载和存储数据。
2.  `LDA` 用于使用 16 位地址(3 字节指令)直接加载累加器。
3.  像 `MOV`、`MVI`、`LDA` 这样的指令就是数据传输指令。
4.  `ADD` 用于添加数据。
5.  `HLT` 用于暂停程序。