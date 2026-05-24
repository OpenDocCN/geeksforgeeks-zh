# 在 Golang 生成随机数

> 原文:[https://www . geesforgeks . org/generating-random-numbers-in-golang/](https://www.geeksforgeeks.org/generating-random-numbers-in-golang/)

Golang 提供了用于生成[伪随机数](https://www.geeksforgeeks.org/pseudo-random-number-generator-prng/)的包数学/兰德。这个包基本上使用一个单一的源，使得每次执行一个程序时都会产生一个确定性的值序列。在这里，如果每次执行需要不同的输出或结果，可以使用 seed 函数来初始化默认的源，它对于多个 goroutines 的并发使用是安全的。它生成一个介于 0 和 n 之间的整数。它只需要一个参数，如果参数小于零，则 n 或上限&会抛出错误。

```go
 RandomInteger := rand.Int()  // generates a random integer
```

**随机范围内:**生成最大值为上限，最小值为下限的范围内的数字。

```go
RandomIntegerwithinRange := rand.Intn(max-min) + min    // range is min to max
```

**兰特。Float64():** 生成 0.0 到 1.0 之间的浮点数，像 rand.Int 一样好用。

```go
RandomFloatingNumber := rand.Float64() // generates a random floating point number 
```

**例:**

```go
// Generating Random Numbers in Golang
package main

import (
    "fmt"
    "math/rand"
    "time"
)

func main() {

    // Intn returns, as an
    // int, a non-negative
    // pseudo-random number in
    // [0,n) from the default Source.
    // i.e. simply call Intn to
    // get the next random integer.
    fmt.Println(rand.Intn(200))
    fmt.Println(rand.Intn(200))
    fmt.Println(rand.Intn(200))
    fmt.Println()

    // Float64 returns, as
    // a float64, a pseudo-random
    // number in [0.0,1.0)
    // from the default Source.
    fmt.Println(rand.Float64())

    // By default, it uses the value 1.
    fmt.Println((rand.Float64() * 8) + 7)
    fmt.Println((rand.Float64() * 8) + 7)
    fmt.Println()

    // Seeding - Go provides a method,
    // Seed(see int64), that allows you
    // to initialize this default sequence.

    // Implementation is slow
    // to make it faster
    // rand.Seed(time.Now().UnixNano())
    // is added. Seed is the current time,
    // converted to int64 by UnixNano.
    // Gives constantly changing numbers
    x1 := rand.NewSource(time.Now().UnixNano())
    y1 := rand.New(x1)

    fmt.Println(y1.Intn(200))
    fmt.Println(y1.Intn(200))
    fmt.Println()

    x2 := rand.NewSource(55)
    y2 := rand.New(x2)
    fmt.Println(y2.Intn(200))
    fmt.Println(y2.Intn(200))
    fmt.Println()

    x3 := rand.NewSource(5)
    y3 := rand.New(x3)
    fmt.Println(y3.Intn(200))
    fmt.Println(y3.Intn(200))
}
```

**输出:**

```go
81
87
47

0.4377141871869802
10.397099976570125
12.494584582936875

0
128

112
164

26
36

```

如果用户想对随机数保密，上述方法是不安全的。这就是为什么 Golang 提供**密码和**来改变未来数字的随机性水平。它是加密就绪的，使用方便，安全，但速度较慢。它用于生成密钥、CSRF 令牌或任何与安全相关的东西。

**例:**

```go
package main

import (
    "crypto/rand"
    "fmt"
)

func main() {
    RandomCrypto, _ := rand.Prime(rand.Reader, 128)
    fmt.Println(RandomCrypto)
}
```

当您执行这段代码时，每次都会得到不同的输出。