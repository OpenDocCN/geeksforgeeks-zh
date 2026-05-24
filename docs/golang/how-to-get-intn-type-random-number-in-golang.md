# 如何在 Golang 中获取 Intn 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-intn-type-随机数 in-golang/](https://www.geeksforgeeks.org/how-to-get-intn-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。

在 math/rand 包提供的 **Intn()函数**的帮助下，您可以从默认来源生成 int 类型的[0，n]中的非负伪随机数。因此，您需要在程序中添加一个 math/rand 包，借助 import 关键字来访问 Intn()函数。如果 n 的值为< = 0，这个方法会出现恐慌。

**语法:**

```go
func Intn(n int) int
```

让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// how to Get Intn Type Random 
// Number
package main

import (
    "fmt"
    "math/rand"
)

// Main function
func main() {

    // Finding random numbers of int type
    // Using Intn() function
    res_1 := rand.Intn(7)
    res_2 := rand.Intn(8)
    res_3 := rand.Intn(2)

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  6
Random Number 2:  7
Random Number 3:  1

```

**例 2:**

```go
// Golang program to illustrate how 
// to get Intn Type Random Number
package main

import (
    "fmt"
    "math/rand"
)

// Function
func intnrandom(value_1, value_2 int) int {
    return value_1 + value_2 + rand.Intn(4)

}

// Main function
func main() {

    // Getting result from Intnrandom() function
    res1 := intnrandom(10, 3)
    res2 := intnrandom(44, 59)
    res3 := intnrandom(130, 50)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  14
Result 2:  106
Result 3:  183

```