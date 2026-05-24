# 计算一个数的阶乘中尾随零的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-程序到计数-数字阶乘中的尾随零/](https://www.geeksforgeeks.org/golang-program-to-count-trailing-zeros-in-factorial-of-a-number/)

给定一个整数 n，编写一个 Go 程序来计算 n 的阶乘中尾随零的个数。

**例:**

```go
Input : 7
Output : 1
Explanation: 7! = 5040, which has 1 trailing zero

Input : 10
Output : 2
Explanation: 10! = 3628800, which has 2 trailing zeros

```

**天真的做法:**对 n 中的尾随零进行计数！，一种方法是找到 n 的阶乘，然后使用循环计算尾随零的数量，并计算(n%10==0)s 的数量。但是，即使对于 20 这样的小数字，阶乘值也足够大，会导致整数溢出。

**有效方法:**要计算尾随零的数量，首先需要了解在一个数的阶乘中是什么导致了尾随零。

数字 10 负责尾随零。10 的素分解是 2*5。在任意数的素分解中，2s 的个数总是大于或等于 5s 的个数。因此，只需要在数的素分解中找到五的个数。

**例 1:** 当 n = 7 时，7 的素分解！是 2^4 * 3^2 * 5^1 * 7^1.素数分解中的 5s 数是 1。因此，在 7！是 1。

**例 2:** 当 n = 10 时，10 的素分解！是 2^8 * 3^4 * 5^2 * 7^1.素数分解中的 5s 数是 2。因此，尾随零的数量在 10！是 2。

> trailingeroscount = floor(n/5)+floor(n/5^2)+floor(n/5^3)+…。+ floor(n/5^k)其中 5^k<= n

t0】

**输出:**

```go
The number of trailing zeros in 10! is 2

```