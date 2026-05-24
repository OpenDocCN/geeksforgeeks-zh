# 完成。Golang 中的 Exp()函数示例

> 原文:[https://www . geesforgeks . org/complx-exp-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-exp-function-in-golang-with-examples/)

**完成。Golang 中的 Exp()函数**用来返回 e**x，x 的基-e 指数。

**语法:**

```go
func Exp(x complex128) complex128

```

这里，x 是所有实数和虚数的集合。

**返回类型:**该函数的返回类型为复数。

**例 1:**

```go
// Golang program to illustrate
// the complx.Exp() Function

package main

// importing fmt and math/cmplx
import (
"fmt"
"math/cmplx"
)

// Calling main method
func main() {

    // using the function
    fmt.Printf("%.2f", cmplx.Exp(5 + 6i))
}
```

**输出:**

```go
(142.50-41.47i)

```

**例 2:**

```go
// Golang program to illustrate
// the complx.Exp() Function

package main

// importing fmt and math/cmplx
import (
"fmt"
"math/cmplx"
)

// Calling main method
func main() {

    n := complex(7, 8)

    // using the function
    fmt.Printf("%.2f", cmplx.Exp(n))
}
```

**输出:**

```go
(-159.56+1084.96i)

```