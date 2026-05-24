# 如何在 Golang 中获取 Float32 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-float 32-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-float32-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。
在 math/rand 软件包提供的 **Float32()函数**的帮助下，您可以从默认来源生成一个 float32 的伪随机数 in [0.0，1.0]。因此，您需要借助 import 关键字在程序中添加一个 math/rand 包。

**语法:**

```go
func Float32() float32
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

    // Finding random numbers of float32 type
    // Using Float32() function
    res_1 := rand.Float32()
    res_2 := rand.Float32()
    res_3 := rand.Float32()

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  0.6046603
Random Number 2:  0.9405091
Random Number 3:  0.6645601

```

**例 2:**

```go
// Go program to illustrate
// the use of the random numbers
package main

import (
    "fmt"
    "math/rand"
)

// Function
func floatrandom(value_1, value_2 float32) float32 {
    return value_1 + value_2 + rand.Float32()

}

// Main function
func main() {

    // Getting result from floatrandom() function
    res1 := floatrandom(23, 6)
    res2 := floatrandom(34, 50)
    res3 := floatrandom(200, 60)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  29.60466
Result 2:  84.940506
Result 3:  260.66455

```