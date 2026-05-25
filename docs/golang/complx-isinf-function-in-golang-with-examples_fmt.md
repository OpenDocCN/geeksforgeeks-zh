# Golang 中的 IsInf()函数示例

> 原文: [https://www.geeksforgeeks.org/complx-isinf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-isinf-function-in-golang-with-examples/)

`IsInf()`函数报告实数(`x`)或虚数(`x`)是否为无穷大。返回值是布尔值。

## 语法:

```go
func IsInf(x complex128) bool
```

这里，`x` 是一个所有实数和虚数部分均为 64 位浮点数的复数集合。

## 返回值:

返回布尔值（真或假）。

## 例 1:

本例检查 `1+5i` 是否为无穷大。

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

## 输出:

```go
false
```

## 例 2:

本例验证变量 `infy` 是否为无穷大。

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

## 输出:

```go
true
```