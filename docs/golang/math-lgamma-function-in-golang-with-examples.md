# Golang 中的 Math.LGamma()函数，示例

> Original: [https://www.geeksforgeeks.org/math-lgamma-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-lgamma-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 此软件包提供**LGamma()函数**，该函数用于查找 Gamma(A)的自然对数和符号(-1 或+1)。 因此，需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 LGamma()函数。

**语法：**

```go
func Lgamma(a float64) (lgamma float64, sign int)
```

*   如果 LGamma(+inf)，则此函数将返回+inf。
*   如果 LGamma(0)，则此函数将返回+inf。
*   如果为 LGamma(-整数)，则此函数将返回+inf。
*   如果 LGamma(-inf)，则此函数将返回-inf。
*   如果是 LGamma(NaN)，则此函数将返回 NaN。

**示例 1：**

```go
// Golang program to illustrate
// math.Lgamma() Function
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the natural logarithm of Gamma()
    // Using Lgamma() function
    res_1, s1 := math.Lgamma(0)
    res_2, s2 := math.Lgamma(-2.3)
    res_3, s3 := math.Lgamma(math.Inf(-2))
    res_4, s4 := math.Lgamma(-2)
    res_5, s5 := math.Lgamma(math.NaN())

    // Displaying the result
    fmt.Printf("\nResult 1: %f and sign: %d", res_1, s1)
    fmt.Printf("\nResult 2: %f and sign: %d", res_2, s2)
    fmt.Printf("\nResult 3: %f and sign: %d", res_3, s3)
    fmt.Printf("\nResult 4: %f and sign: %d", res_4, s4)
    fmt.Printf("\nResult 5: %f and sign: %d", res_5, s5)
}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: +Inf and sign: 1
Result 2: 0.369567 and sign: -1
Result 3: -Inf and sign: 1
Result 4: +Inf and sign: 1
Result 5: NaN and sign: 1

```

**示例 2：**

```go
// Golang program to illustrate
// math.Lgamma() Function

package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding the natural logarithm of Gamma()
    // Using Lgamma() function
    nvalue_1, sign_1 := math.Lgamma(1.5)
    nvalue_2, sign_2 := math.Lgamma(3.45)

    // Finding the sum of the 
    // natural logarithm of Gamma()
    res := nvalue_1 + nvalue_2
    fmt.Printf("Result 1: %f and sign: %d", nvalue_1, sign_1)
    fmt.Printf("\nResult 2: %f and sign: %d \n", nvalue_2, sign_2)
    fmt.Println("Sum of Result 1 and Result 2: ", res)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1: -0.120782 and sign: 1
Result 2: 1.146231 and sign: 1 
Sum of Result 1 and Result 2:  1.0254487526135667

```