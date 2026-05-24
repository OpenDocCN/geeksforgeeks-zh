# 完成。Golang 中的 Pow()函数示例

> 原文:[https://www . geesforgeks . org/complx-power-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-pow-function-in-golang-with-examples/)

**完成。Golang 中的 Pow()函数**用来求 x**y，y 的基-x 指数，对于这个函数，需要导入“math/cmplx”包。

**语法:**

```go
func Pow(x, y complex128) complex128
```

*   Pow (0,0) returns 1+0i
*   Pow(0, c) is a real number (c) < 0 returns Inf+0i if imag(c) is zero, otherwise INF+INF I.

**参数:**使用的参数是两个复数，其中 complex128 是所有实数和虚数部分都为 float64 的复数的集合。这个函数的返回类型也是一个复数。

**例 1:**

```go
package main

import (
    "fmt"
    "math/cmplx"
)

func main() {
    var a complex128
    var b complex128
    a= complex(2,5)
    b= complex(3,7)
    fmt.Println(cmplx.Pow(a,b))
}
```

**输出:**

```go
(-0.03528847161704272+0.0129436389603905i)
```

**例 2:**

```go
// Golang program to illustrate
// the complx.Pow() Function

package main

import (
    "fmt"
    "math/cmplx"
)

func main() {
    var a complex128
    var b complex128
    a= complex(1,2)
    b= complex(1,0)

    // using the function
    fmt.Println(cmplx.Pow(a,b))
}
```

**输出:**

```go
(1.0000000000000002+2i)
```