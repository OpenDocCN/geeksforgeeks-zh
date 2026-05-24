# 完成。Golang 中的 Phase()函数示例

> 原文:[https://www . geesforgeks . org/complx-phase-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-phase-function-in-golang-with-examples/)

在 Go 语言中，cmplx 包为复数提供基本常数和数学函数。Go 语言中的 **Phase()函数**用于返回给定数字的相位(也称为自变量)。此外，该功能是在 cmplx 包中定义的。在这里，您需要导入“math/cmplx”包才能使用这些函数。

**语法:**

```go
func Phase(x complex128) float64

```

返回值在[-π，π]范围内。

**例 1:**

```go
// Golang program to illustrate the complex.Phase() function

package main

import (
    "fmt"
    "math"
    "math/cmplx"
)

// Main function 
func main() {

    // using the function
    fmt.Printf("%.1f", cmplx.Phase(1i*math.Pi)+1)
}
```

**输出:**

```go
2.6

```

**例 2:**

```go
// Golang program to illustrate the complex.Phase() function

package main

import (
    "fmt"
    "math"
    "math/cmplx"
)

// Main function
func main() {

    // using the function
    fmt.Printf("%.1f, ", cmplx.Phase(1i*math.Pi))
    fmt.Printf("%.1f", cmplx.Phase(2i*math.Pi)+3)
}
```

**输出:**

```go
1.6, 4.6

```