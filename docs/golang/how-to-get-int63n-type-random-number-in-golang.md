# 如何在 Golang 中获取 Int63n 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-int 63n-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-int63n-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。

在 math/rand 包提供的 **Int63n()函数**的帮助下，您可以从缺省源生成一个 63 位整数 n 的非负伪随机数 in [0，n]作为 int64 类型。因此，您需要借助 import 关键字在程序中添加一个 math/rand 包来访问 Int63n()函数。如果 n 的值为< = 0，这个方法会出现恐慌。

**语法:**

```go
func Int63n(n int64) int64
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate how to
// get int63n type random number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Finding random numbers of int63n type
    // Using Int63n() function
    res_1 := rand.Int63n(7)
    res_2 := rand.Int63n(3)
    res_3 := rand.Int63n(1)

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  5
Random Number 2:  1
Random Number 3:  0

```

**例 2:**

```go
// Golang program to illustrate how to
// get int63n type random number
package main

import (
    "fmt"
    "math/rand"
)

// Function
func int63nrandom(value_1, value_2 int64) int64 {
    return value_1 + value_2 + rand.Int63n(4)

}

// Main function
func main() {

    // Getting result from Int63nrandom() function
    res1 := int63nrandom(10, 3)
    res2 := int63nrandom(430, 56)
    res3 := int63nrandom(13, 500)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  15
Result 2:  489
Result 3:  514

```