# Golang 中的 math.Ilogb()函数，示例为

> Original: [https://www.geeksforgeeks.org/math-ilogb-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-ilogb-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 借助数学包提供的**ILogb()函数**，您可以找到指定数字的二进制指数作为整数。 因此，需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 ILogb()函数。

**语法：**

```go
func Ilogb(a float64) int
```

*   如果 Ilogb(±inf)，则此函数将返回 MaxInt32。
*   如果 Ilogb(0)，则此函数将返回 MinInt32。
*   如果为 Ilogb(NaN)，则此函数将返回 MaxInt32。

**示例 1：**

```go
// Golang program to illustrate
// the math.Ilogb() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding binary exponent of 
    // the given number as an integer
    // Using Ilogb() function
    res_1 := math.Ilogb(math.Inf(-1))
    res_2 := math.Ilogb(math.Inf(1))
    res_3 := math.Ilogb(0)
    res_4 := math.Ilogb(1)
    res_5 := math.Ilogb(math.NaN())

    // Displaying the result
    fmt.Printf("\nResult 1: %d", res_1)
    fmt.Printf("\nResult 2: %d", res_2)
    fmt.Printf("\nResult 3: %d", res_3)
    fmt.Printf("\nResult 4: %d", res_4)
    fmt.Printf("\nResult 5: %d", res_5)
}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 2147483647
Result 2: 2147483647
Result 3: -2147483648
Result 4: 0
Result 5: 2147483647

```

**示例 2：**

```go
// Golang program to illustrate
// the math.Ilogb() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding binary exponent of 
    // the given number as an integer
    // Using Ilogb() function
    nvalue_1 := math.Ilogb(math.Inf(-1))
    nvalue_2 := math.Ilogb(math.Inf(1))

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%d + %d = %d", 
       nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
2147483647 + 2147483647 = -2
```