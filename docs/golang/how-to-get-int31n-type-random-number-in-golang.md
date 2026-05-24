# 如何在 Golang 中获取 Int31n 型随机数？

> 原文:[https://www . geesforgeks . org/how-to-get-int 31n-type-random-number-in-golang/](https://www.geeksforgeeks.org/how-to-get-int31n-type-random-number-in-golang/)

Go 语言在 math/rand 包的帮助下，为生成指定类型的随机数提供了内置支持。这个包实现了伪随机数生成器。这些随机数是由一个源生成的，每次程序运行时，这个源都会生成一个确定性的值序列。而且如果你想将随机数用于安全敏感的工作，那么就使用 crypto/rand 包。
在 math/rand 软件包提供的 **Int31n()函数**的帮助下，您可以从默认来源生成一个 31 位整数 n 的非负伪随机数 in [0，n]作为 int32 类型。因此，您需要借助 import 关键字在程序中添加一个 math/rand 包来访问 Int31()函数。如果 n 的值是< = 0，这个方法会[恐慌](https://www.geeksforgeeks.org/panic-in-golang/)。

**语法:**

```go
func Int31n(n int32) int32
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

    // Finding random numbers of int31n type
    // Using Int31n() function
    res_1 := rand.Int31n(2)
    res_2 := rand.Int31n(4)
    res_3 := rand.Int31n(1)

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)
    fmt.Println("Random Number 3: ", res_3)
}
```

**输出:**

```go
Random Number 1:  1
Random Number 2:  3
Random Number 3:  0

```

**例 2:**

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

    // If the value of this function
    // is 0 or less than zero
    // the this method will panics
    res_1 := rand.Int31n(0)
    res_2 := rand.Int31n(-1)

    // Displaying the result
    fmt.Println("Random Number 1: ", res_1)
    fmt.Println("Random Number 2: ", res_2)

}
```

**输出:**

> 死机:Int31n 的参数无效
> 
> gor routine 1[运行]:t0]数学/边缘。(* rand). int 31n(0x 43 和 280.0x 0.0x 43 和 280.0x 46000)
> /usr/local/go/src/math/rand/rand . go:128+0x 180
> math/rand。int 31n(…)/usr/local/go/src/math/rand/rand . go:324
> main . main()
> /tmp/sandbox 269134149/Prog . go:16+0x 40