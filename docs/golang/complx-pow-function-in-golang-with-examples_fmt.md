# Golang 中的 Pow() 函数示例

> 原文: [https://www.geeksforgeeks.org/complx-pow-function-in-golang-with-examples/](https://www.geeksforgeeks.org/complx-pow-function-in-golang-with-examples/)

`Pow()` 函数用于求 x 的 y 次幂（基-x 指数）。使用此函数需要导入 `math/cmplx` 包。

## 语法

```go
func Pow(x, y complex128) complex128
```

*   `Pow(0, 0)` 返回 `1+0i`。
*   `Pow(0, c)` 是一个实数。如果 `c < 0` 且 `imag(c)` 为零，则返回 `Inf+0i`，否则返回 `Inf+Inf i`。

## 参数

使用的参数是两个 `complex128` 类型的复数。`complex128` 是实部和虚部均为 `float64` 的复数集合。该函数的返回类型也是一个复数。

## 例 1

```go
package main

import (
    "fmt"
    "math/cmplx"
)

func main() {
    var a complex128
    var b complex128
    a = complex(2, 5)
    b = complex(3, 7)
    fmt.Println(cmplx.Pow(a, b))
}
```

### 输出

```go
(-0.03528847161704272+0.0129436389603905i)
```

## 例 2

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
    a = complex(1, 2)
    b = complex(1, 0)

    // using the function
    fmt.Println(cmplx.Pow(a, b))
}
```

### 输出

```go
(1.0000000000000002+2i)
```