# Golang 中的 math.Atan2()函数，示例为

> Original: [https://www.geeksforgeeks.org/math-atan2-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-atan2-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 借助数学包提供的**Atan2()函数**，您可以找到 a/b 的反正切线，使用这两个符号来标识返回值的象限。 因此，需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 Atan2()函数。

**语法：**

```go
func Atan2(b, a float64) float64
```

*   如果是 Atan2(b，NaN)，则此方法将返回 NaN。
*   如果是 Atan2(NaN，a)，则此方法将返回 NaN。
*   如果 Atan2(+0，a>=0)，则此方法将返回+0。
*   如果 Atan2(-0，a>=0)，则此方法将返回-0。
*   如果 Atan2(+0，a<=0)，则此方法将返回+PI。
*   如果 Atan2(-0，a<=0)，则此方法将返回-Pi。
*   如果 Atan2(b>0，0)，则此方法将返回+Pi/2。
*   如果 Atan2(b<0，0)，则此方法将返回-Pi/2。
*   如果 Atan2(+inf，+inf)，则此方法将返回+PI/4。
*   如果 Atan2(-inf，+inf)，则此方法将返回-PI/4。
*   如果 Atan2(+inf，-inf)，则此方法将返回-3Pi/4。
*   如果 Atan2(+inf，+inf)，则此方法将返回 0。
*   如果 Atan2(b，+inf)，则此方法将返回+Pi/4。
*   如果 Atan2(b>0，-inf)，则此方法将返回+Pi。
*   如果 Atan2(b<0，-inf)，则此方法将返回-Pi。
*   如果 Atan2(+inf，a)，则此方法将返回+Pi/2。
*   如果 Atan2(-inf，a)，则此方法将返回-Pi/2。

**示例 1：**

```go
// Golang program to illustrate 
// the math.Atan2() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arc tangent
    // Using Atan2() function
    res_1 := math.Atan2(math.Pi/3, math.Pi/4)
    res_2 := math.Atan2(math.Inf(1), 0)
    res_3 := math.Atan2(math.Inf(-2), math.Inf(+2))
    res_4 := math.Atan2(1, math.NaN())
    res_5 := math.Atan2(math.NaN(), 0)

    // Displaying the result
    fmt.Printf("\nResult 1: %.1f", res_1)
    fmt.Printf("\nResult 2: %.1f", res_2)
    fmt.Printf("\nResult 3: %.1f", res_3)
    fmt.Printf("\nResult 4: %.1f", res_4)
    fmt.Printf("\nResult 5: %.1f", res_5)
}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: 0.9
Result 2: 1.6
Result 3: -0.8
Result 4: NaN
Result 5: NaN

```

**示例 2：**

```go
// Golang program to illustrate
// the math.Atan2() function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding arc tangent
    // Using Atan2() function
    nvalue_1 := math.Atan2(math.Pi/3, math.Pi/4)
    nvalue_2 := math.Atan2(math.Pi/6, math.Pi/3)

    // Sum of the given numbers
    res := nvalue_1 + nvalue_2
    fmt.Printf("%.2f + %.2f = %.2f",
            nvalue_1, nvalue_2, res)

}
```

发帖主题：Re：Колибри0.7.0

```go
0.93 + 0.46 = 1.39
```