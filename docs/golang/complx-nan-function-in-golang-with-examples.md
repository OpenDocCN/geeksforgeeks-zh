# 完成。NaN()函数在 Golang 中的应用举例

> 原文:[https://www . geesforgeks . org/complx-nan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-nan-function-in-golang-with-examples/)

**完成。Golang 中的 NaN()函数**用于返回一个复杂的“非数字”值。

**语法:**

```go
func NaN() complex128

```

它返回复杂的 NaN 值。让我们借助给定的例子来讨论这个概念:

**例 1:**

```go
// Golang program to illustrate
// the complx.NaN() Function

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {

    // Using the function
    fmt.Printf("%.1f", cmplx.NaN())
}
```

**输出:**

```go
(NaN+NaNi)

```

**例 2:**

```go
// Golang program to illustrate
// the complx.NaN() Function

package main

import (
    "fmt"
    "math/cmplx"
)

// Main function
func main() {
    // checking if the generated value is Not-a-number or not?
    fmt.Printf("%t", cmplx.IsNaN(cmplx.NaN()))

}
```

**输出:**

```go
true

```