# 如何在 Golang 中获取 Uint32 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-uint 32-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-uint32-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。

在 math/rand 软件包提供的 **Uint32()函数**的帮助下，您可以从默认来源生成一个 32 位整数的伪随机数作为 uint32 类型。因此，您需要在导入关键字的帮助下在程序中添加一个 math/rand 包来访问 *Uint32()函数*。

**语法:**

```go
func Uint32() uint32
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
    // Using Uint32() function
    res_1 := rand.Uint32()
    res_2 := rand.Uint32()
    res_3 := rand.Uint32()

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  2596996162
Random Number 2:  4039455774
Random Number 3:  2854263694

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
func uint32random(value_1, value_2 uint32) uint32 {
    return value_1 + value_2 + rand.Uint32()

}

// Main function
func main() {

    // Getting result from uint32random() function
    res1 := uint32random(10, 3)
    res2 := uint32random(44, 59)
    res3 := uint32random(130, 50)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  2596996175
Result 2:  4039455877
Result 3:  2854263874

```