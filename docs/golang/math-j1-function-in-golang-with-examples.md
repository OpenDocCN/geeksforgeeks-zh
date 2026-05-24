# Golang 中的 math.j1()函数，示例

> Original: [https://www.geeksforgeeks.org/math-j1-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-j1-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 借助数学包提供的**J1()函数**，您可以找到第一类的一阶贝塞尔函数。 因此，您需要在程序中添加一个数学包，并借助 import 关键字来访问 J1()函数。

**语法：**

```go
func J1(a float64) float64
```

*   如果 j1(±inf)，则此函数将返回 0。
*   如果为 j1(NaN)，则此函数将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate
// the math.J1() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding order-one Bessel 
    // function of the first kind
    // Using J1() function
    res_1 := math.J1(math.Inf(-1))
    res_2 := math.J1(math.Inf(1))
    res_3 := math.J1(4)
    res_4 := math.J1(math.NaN())

    // Displaying the result
    fmt.Printf("\nResult 1: %.2f", res_1)
    fmt.Printf("\nResult 2: %.2f", res_2)
    fmt.Printf("\nResult 3: %.2f", res_3)
    fmt.Printf("\nResult 4: %.2f", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 0.00
Result 2: 0.00
Result 3: -0.07
Result 4: NaN

```

**示例 2：**

```go
// Golang program to illustrate
// the math.J1() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding order-one Bessel 
    // function of the first kind
    // Using J1() function
    nvalue_1 := math.J1(2.0)
    nvalue_2 := math.J1(4.1)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
            nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
0.58 + -0.10 = 0.47
```