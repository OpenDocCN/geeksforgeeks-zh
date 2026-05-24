# 完成。格朗 IsNaN()函数示例

> 原文:[https://www . geesforgeks . org/complx-isnan-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-isnan-function-in-golang-with-examples/)

在 Go 语言中， *cmplx* 包为复数提供基本常数和数学函数。Go 语言中的 **IsNaN()** 函数用于检查所述实数(x)或 imag(x)是否为 NaN，并且既不是无穷大。此外，该功能是在 cmplx 包中定义的。在这里，您需要导入“math/cmplx”包才能使用这些函数。

**语法:**

```go
func IsNaN(x complex128) bool

```

这里，x 是所有复数的集合，除了虚部之外还有实部。

**返回值:**如果 x 是 NaN 则返回 true，否则返回 false。

**例 1:**

```go
// Golang program to illustrate the usage of
// IsNaN() function

// Including main package
package main

// Importing fmt and math/cmplx
import (
    "fmt"
    "math/cmplx"
)

// Calling main
func main() {

    // Returns output
    fmt.Println(cmplx.IsNaN(3 + 4i))
}
```

**输出:**

```go
false

```

**例 2:**

```go
// Golang program to illustrate the usage of
// IsNaN() function

// Including main package
package main

// Importing fmt and math/cmplx
import (
    "fmt"
    "math/cmplx"
)

// Calling main
func main() {

    // Returns output
    fmt.Println(cmplx.IsNaN(-0i / 8))
}
```

**输出:**

```go
false

```