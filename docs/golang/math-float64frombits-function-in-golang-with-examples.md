# Golang 中的 math.Float64from mbits()函数，示例为

> Original: [https://www.geeksforgeeks.org/math-float64frombits-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-float64frombits-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 此软件包提供**Float64from mbits()函数**，该函数返回与 IEEE 754 二进制表示 a 对应的浮点数，符号位为 a，结果位于相同的位位置。 因此，需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 Float64frombits()函数。

**语法：**

```go
func Float64frombits(a uint64) float64
```

**示例 1：**

```go
// Golang program to illustrate how to find
// the floating-point number corresponding
// to the IEEE 754 binary representation
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding floating-point number corresponding
    // to the IEEE 754 binary representation 
    // of the given numbers
    // Using Float64frombits() function
    res_1 := math.Float64frombits(2)
    res_2 := math.Float64frombits(1)
    res_3 := math.Float64frombits(0)
    res_4 := math.Float64frombits(23)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
    fmt.Println("Result 4: ", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  1e-323
Result 2:  5e-324
Result 3:  0
Result 4:  1.14e-322

```

**示例 2：**

```go
// Golang program to illustrate how to find
// the floating-point number corresponding
// to the IEEE 754 binary representation
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // Finding floating-point number corresponding
    // to the IEEE 754 binary representation
    // of the given numbers
    // Using Float64frombits() function
    nvalue_1 := math.Float64frombits(3)
    nvalue_2 := math.Float64frombits(50)

    // Sum of the given values
    res := nvalue_1 + nvalue_2
    fmt.Println("Result 1: ", nvalue_1)
    fmt.Println("Result 2: ", nvalue_2)
    fmt.Println("Sum of Result 1 and Result 2: ", res)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  1.5e-323
Result 2:  2.47e-322
Sum of Result 1 and Result 2:  2.6e-322

```