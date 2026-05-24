# Golang 中的按位非运算符

> 原文:[https://www . geesforgeks . org/bitwise-not-operator-in-golang/](https://www.geeksforgeeks.org/bitwise-not-operator-in-golang/)

编程世界中的按位非运算符通常取一个数字，并返回该数字的反转位，如下所示:

```go
Bitwise NOT of 1 = 0
Bitwise NOT of 0 = 1

```

**示例:**

```go
Input : X = 010101
Output : Bitwise NOT of X = 101010

```

但是 Golang 没有任何指定的一元 Bitwise NOT(~)或者你可以像其他编程语言(C/C++、Java、Python 等)一样说 Bitwise Complement 运算符。这里，您必须使用**按位 XOR(^)运算符作为按位非运算符**。但是怎么做呢？

让我们了解一下按位异或是如何接受任意两个等长的位模式，并对每对对应的位执行异或运算的。

```go
1 XOR 1 = 0 
1 XOR 0 = 1 
0 XOR 0 = 0
0 XOR 1 = 1 

```

这里可以看到 ***异或(M，N) = 1 的结果只有 M！= N 否则将为 0*** 。所以在这里，我们将使用异或运算符作为一元运算符来实现一个数的补码。
在 Golang 中，假设您有一个给定的位 m，那么 **^M = 1 ^ M** 将等于一的补码，或者您可以说按位非运算符结果。

**示例:**假设给定的位为 010101。

```go
Input: 11111111 XOR 00001111
Output: 11110000

```

```go

package main

import "fmt"

func main() {

    // taking the number in the hexadecimal
    // form it is 15 i.e. 00001111 in 8-bit form
    var bitwisenot byte = 0x0F

    // printing the number in 8-Bit
    fmt.Printf("%08b\n", bitwisenot) 

    // using the ^M = 1 ^ M
    fmt.Printf("%08b\n", ^bitwisenot)
}
```

**输出:**

```go
00001111
11110000

```

在这里，你可以看到，如果我们简单地求解 00001111 的按位非，那么它将等于 11110000。