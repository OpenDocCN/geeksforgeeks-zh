# 如何在 Golang 中获取 Int 型随机数？

> 原文:[https://www . geesforgeks . org/how-get-int-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-int-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每当程序运行时，这个源都会产生一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。
在 math/rand 包提供的 **Int()函数**的帮助下，您可以从默认来源生成整数类型的非负伪随机数。因此，您需要在程序中添加一个 math/rand 包，借助 import 关键字来访问 *Int()函数*。

**语法:**

```go
func Int() int
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang Program to illustrate
// how to get a random number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Finding random numbers of int type
    // Using Int() function
    res_1 := rand.Int()
    res_2 := rand.Int()
    res_3 := rand.Int()

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
Random Number 3:  6129484611666145821

```

**例 2:**

```go
// Golang program to illustrate
// the use of the random numbers
package main

import (
    "fmt"
    "math/rand"
)

// Function
func intrandom(value_1, value_2 int) int {
    return value_1 + value_2 + rand.Int()

}

// Main function
func main() {

    // Getting result from intrandom() function
    res1 := intrandom(2, 6)
    res2 := intrandom(49, 50)
    res3 := intrandom(120, 98)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  5577006791947779418
Result 2:  8674665223082153650
Result 3:  6129484611666146039

```