# 8085 程序判断数字是否为质数

> 原文: [https://www.geeksforgeeks.org/8085-program-to-determine-if-the-number-is-prime-or-not/](https://www.geeksforgeeks.org/8085-program-to-determine-if-the-number-is-prime-or-not/)

## 问题
用 8085 微处理器编写一个汇编语言程序，判断给定的数是否是素数。

如果数字是质数，在存储结果的存储位置存储 `01H`，否则存储 `00H`。

## 示例
```
Input : 03H
Output : 01H
The number 3 only has two divisors, 1 and 3. 
Hence, it is prime.
Input : 09H
Output : 00H
The number 9 has three divisors, 1, 3 and 9. 
Hence, it is composite.
```

![img/ccb75557f65c5e5b01ec378f39d80843.png](img/ccb755557f65c5e5b01ec378f39d80843.png)

质数是只有两个除数的数，1 和数本身。
另一方面，一个复合数有 3 个或更多除数。

## 算法
1.  以 `n` 为输入
2.  运行从 `i = n` 到 1 的循环。对于每一次迭代，检查 `i` 是否完全除 `n`。如果是，那么 `i` 就是 `n` 的除数
3.  记录除数的总数
4.  如果除数是 2，那么这个数就是质数，否则就是复合数

## 如何找出 `i` 是不是除数？
继续从股息中减去 `i`，直到股息变为 0 或小于 0。现在，检查红利的价值。如果是 0，那么 `i` 是除数，否则不是。

## 步骤
1.  将数据从内存位置 (`2029H`，任意选择) 加载到累加器中
2.  用 `00H` 初始化寄存器 `C`。这存储了 `n` 的除数
3.  在 `e` 中移动累加器中的值。这将作为从 `n` 到 1 的循环的迭代器。
4.  移动 `B` 中累加器的值。`B` 永久存储 `n`，因为累加器中的值会改变
5.  将 `E` 中的值移动到 `D`，用累加器作为被除数，`D` 作为除数进行除法运算。
6.  除法: 继续从 `A` 中减去 `D`，直到 `A` 中的值变成 0 或小于 0。此后，检查累加器中的值。如果它等于 0，那么通过将 `C` 中的值增加 1 来增加除数
7.  通过将 `B` 中的值移动到 `A` 来恢复累加器的值，并继续循环，直到 `E` 变为 0
8.  现在，把除数从 `C` 移到 `A`，检查它是否等于 2。如果是，则存储 `01H` 到 `202AH` (任意)，否则存储 `00H`。

`202AH` 包含结果。

```
| 地址   | 标签                 | 记忆的       |
|--------|----------------------|--------------|
| 2000H  |                      | LDA 2029H    |
| 2001H  |                      |              |
| 2002H  |                      |              |
| 2003H  |                      | MVI C, 00H   |
| 2004H  |                      |              |
| 2005H  |                      | MOV E, A     |
| 2006H  |                      | MOV B, A     |
| 2007H  | LOOP1                | MOV D, E     |
| 2008H  | LOOP2                | CMP D        |
| 2009H  |                      | JC DIVIDENDLESSTHAN0 |
| 200AH  |                      |              |
| 200BH  |                      |              |
| 200CH  |                      | SUB D        |
| 200DH  |                      | JNZ LOOP2    |
| 200EH  |                      |              |
| 200FH  |                      |              |
| 2010H  | DIVIDENDLESSTHAN0    | CPI 00H      |
| 2011H  |                      |              |
| 2012H  |                      | JNZ NOTADIVISOR |
| 2013H  |                      |              |
| 2014H  |                      |              |
| 2015H  |                      | INR C        |
| 2016H  | NOTADIVISOR          | MOV A, B     |
| 2017H  |                      | DCR E        |
| 2018H  |                      | JNZ LOOP1    |
| 2019H  |                      |              |
| 201AH  |                      |              |
| 201BH  |                      | MOV A, C     |
| 201CH  |                      | MVI C, 00H   |
| 201DH  |                      |              |
| 201EH  |                      | CPI 02H      |
| 201FH  |                      |              |
| 2020H  |                      | JNZ COMPOSITE |
| 2021H  |                      |              |
| 2022H  |                      |              |
| 2023H  |                      | INR C        |
| 2024H  | COMPOSITE            | MOV A, C     |
| 2025H  |                      | STA 202AH    |
| 2026H  |                      |              |
| 2027H  |                      |              |
| 2028H  |                      | HLT          |
```

将 `n` 的值存储在 `2029H`。如果 `202AH` 包含 `01H`，则 `n` 是质数，否则是合数。