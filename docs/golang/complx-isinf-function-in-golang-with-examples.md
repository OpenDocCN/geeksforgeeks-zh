# 完成。Golang 中的 IsInf()函数示例

> 原文:[https://www . geeksforgeeks . org/complx-is if-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-isinf-function-in-golang-with-examples/)

**完成。Golang 中的 IsInf()函数**报告是实数(x)还是 imag(x)是无穷大。返回值是布尔值。

**语法:**

```go
func IsInf(x complex128) bool

```

这里，x 是所有实数和虚数都有 64 个浮点数的集合。

**返回值:**返回布尔值，真或假。

**例 1:** 本例检查 1+5i 是否为无穷大。

```go
// Golang program to illustrate
// the complx.IsInf() Function

package main

// importing fmt and math/cmplx
import (
    "fmt"
    "math/cmplx"
)

// Calling Main()
func main() {

        // creating a complex number 1 + 5i
    infy := complex(1, 5)  

    // checking if it is infinity or not?  
    fmt.Printf("%t", cmplx.IsInf(infy)) 
}
```

**输出:**

```go
false

```

**例 2:** 本例验证 var infy 是否为无穷大。

```go
// Golang program to illustrate
// the complx.IsInf() Function

package main

// importing fmt and math/cmplx
import (
    "fmt"
    "math"
    "math/cmplx"
)

// Calling Main method
func main() {
    // creating infinity variable.
    inf := math.Inf(1)

    // creating infinity complex
    // number i.e. (INF + INFi)
    infy := complex(inf, inf)
    // checking if it is infinity.
    fmt.Printf("%t", cmplx.IsInf(infy))
}
```

**输出:**

```go
true

```