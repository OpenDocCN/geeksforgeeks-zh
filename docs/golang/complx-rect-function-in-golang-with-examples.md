# 完成。Golang 中的 Rect()函数示例

> 原文:[https://www . geesforgeks . org/complx-rect-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-rect-function-in-golang-with-examples/)

**完成。Golang 中的 Rect()函数**返回极坐标为 r，θ的复数 x。它以浮点值为输入，返回复数。这种方法属于复杂包装。

**语法:**

```go
func Rect(r, θ float64) complex128;

```

这里，r 和θ是实数和虚数都为 64 的复数。

**返回值:**返回极坐标 r 和θ的复数。

**示例 1:** 本示例通过传递参数(5，45)来计算值。

```go
// Golang program to illustrate
// the complx.Rect() Function

 package main 

// importing fmt and math/cmplx
  import (
      "fmt" 
      "math/cmplx" 
) 

    // Calling Main method
    func main () {

    // using the function
    fmt.Printf ("%.1f", cmplx.Rect (5, 45)) 
}
```

**输出:**

```go
(2.6+4.3i)

```

**例 2:**

```go
// Golang program to illustrate
// the complx.Rect() Function

 package main

// importing fmt, math and math/cmplx
import (
"fmt"
"math"
"math/cmplx"
)

// Calling Main method
func main() {

    // using the function   
    fmt.Printf("%.1f,", cmplx.Rect(5, 4*math.Pi)) 
    fmt.Printf("%.1f", cmplx.Rect(5, 90))
}
```

**输出:**

```go
(5.0-0.0i),(-2.2+4.5i)

```