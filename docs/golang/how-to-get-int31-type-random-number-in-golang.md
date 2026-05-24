# 如何在 Golang 中获取 Int31 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-int 31-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-int31-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。

您可以借助 math/rand 包提供的 **Int31()函数**从默认来源生成 31 位整数的非负伪随机数作为 int32 类型。因此，您需要借助 import 关键字在程序中添加一个 math/rand 包来访问 Int31()函数。

**语法:**

```go
func Int31() int32
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

    // Finding random numbers of int type
    // Using Int31() function
    res_1 := rand.Int31()
    res_2 := rand.Int31()
    res_3 := rand.Int31()

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  1298498081
Random Number 2:  2019727887
Random Number 3:  1427131847

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
func int31random(value_1, value_2 int32) int32 {
    return value_1 + value_2 + rand.Int31()

}

// Main function
func main() {

    // Getting result from int31random() function
    res1 := int31random(2, 9)
    res2 := int31random(47, 20)
    res3 := int31random(400, 98)

    // Displaying results
    fmt.Println("Result 1: ", res1)
    fmt.Println("Result 2: ", res2)
    fmt.Println("Result 3: ", res3)
}
```

**输出:**

```go
Result 1:  1298498092
Result 2:  2019727954
Result 3:  1427132345

```