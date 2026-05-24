# 完成。Golang 中的 Inf()函数及示例

> 原文:[https://www . geesforgeks . org/complx-INF-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-inf-function-in-golang-with-examples/)

**完成。Golang 中的 Inf()函数**用来返回一个复无穷，复(+Inf，+Inf)。要使用此功能，必须需要导入“数学/cmplx”包。

**语法:**

```go
func Inf() complex128
```

**返回类型:**返回复无穷。

**例 1:**

```go
// Golang program to illustrate
// the complx.Inf() Function

package main

// importing fmt and math/cmplx
import (
    "fmt"
    "math/cmplx"
)

// calling main method
func main() {

    // returns the complex Infinite number
    fmt.Printf("%f", cmplx.Inf())
}
```

**输出:**

```go
(+Inf+Infi)

```

**例 2:** 你也可以生成一个如下所示的复数无穷大

```go
// Golang program to generate
// complex infinite number

package main

// importing fmt and math
import (
    "fmt"
    "math"
)

// calling main method
func main() {

    // returns a infinite value
    inf := math.Inf(1)

    // make a complex infinite number
    cmp := complex(inf, inf)

    // print the number
    fmt.Printf("%f", cmp)
}
```

**输出:**

```go
(+Inf+Infi)

```