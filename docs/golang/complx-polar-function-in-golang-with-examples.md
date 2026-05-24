# 完成。Golang 中的 Polar()函数示例

> 原文:[https://www . geesforgeks . org/complx-polar-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-polar-function-in-golang-with-examples/)

**完成。Golang 中的 Polar()函数**返回 x 的绝对值 r 和相位θ，相位θ将在[-Pi，Pi]范围内。

**语法:**

```go
func Polar(x complex128) (r, θ float64)

```

这里，x 是一个复数。

**返回值:**返回值在[-Pi，Pi]范围内。

**例 1:**

```go
// Golang program to illustrate
// the complx.Polar() Function

package main

// importing fmt, math and math/cmplx
import (
"fmt"
"math"
"math/cmplx"
)

// Calling Main
func main() {

    // getting the r and theta value
    r, theta := cmplx.Polar(7i) 

    // calculate the value in Pi format.
    p := theta/math.Pi 

    // printing the values r and p.
    fmt.Printf("rValue: %.1f, pValue: %.1f*Pi", r, p) 
}
```

**输出:**

```go
rValue: 7.0, pValue: 0.5*Pi

```

**例 2:**

```go
// Golang program to illustrate
// the complx.Polar() Function

package main

// importing fmt, math and math/cmplx
import (
"fmt"
"math"
"math/cmplx"
)

// Calling Main
func main() {

    // We can create a complex number like this also.   
    n := complex(5, 6)

    // getting the r and theta value of complex number 5 + 6i
    r, theta := cmplx.Polar(n)

    // calculate the value in Pi format.
    p := theta/math.Pi 

    // printing the values r and p.
    fmt.Printf("rValue: %.1f, pValue: %.1f*Pi", r, p) 
}
```

**输出:**

```go
rValue: 7.8, pValue: 0.3*Pi

```