# 如何在 Golang 中获取 Uint64 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-uint 64-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-uint64-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每当程序运行时，这个源都会产生一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。

在 math/rand 包提供的 uint64()函数的帮助下，您可以从默认源生成 64 位整数的伪随机数作为 Uint64 类型。因此，您需要借助 import 关键字在程序中添加一个 math/rand 包来访问 Uint64()函数。

**语法:**

```go
func Uint64() uint64
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// how to get a random number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Finding random numbers
    // Using Uint64() function
    res_1 := rand.Uint64()
    res_2 := rand.Uint64()
    res_3 := rand.Uint64()

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  5577006791947779410
Random Number 2:  8674665223082153551
Random Number 3:  15352856648520921629

```

**例 2:**

```go
// Golang program to illustrate the
// use of the random numbers
package main

import (
    "fmt"
    "math/rand"
)

// Function
func uint64random(value_1, value_2 uint64) uint64 {
    return value_1 + value_2 + rand.Uint64()

}

// Main function
func main() {

    // Getting result from uint32random() function
    res1 := uint64random(10, 3)
    res2 := uint64random(44, 59)
    res3 := uint64random(130, 50)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  5577006791947779423
Result 2:  8674665223082153654
Result 3:  15352856648520921809

```