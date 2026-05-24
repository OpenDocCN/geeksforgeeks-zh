# Golang 中的 math.Float32from mbits()函数，示例为

> Original: [https://www.geeksforgeeks.org/math-float32frombits-function-in-golang-with-examples/](https://www.geeksforgeeks.org/math-float32frombits-function-in-golang-with-examples/)

Go 语言提供了对基本常量和数学函数的内置支持，以便在数学包的帮助下对数字执行运算。 此软件包提供**Float32from mbits()函数**，该函数返回与 IEEE 754 二进制表示 a 对应的浮点数，符号位为 a，结果位于相同的位位置。 因此，您需要在 IMPORT 关键字的帮助下在程序中添加一个数学包来访问 Float32frombits()函数。

**语法：**

```go
func Float32frombits(a uint32) float32
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
    // Using Float32frombits() function
    res_1 := math.Float32frombits(2)
    res_2 := math.Float32frombits(1)
    res_3 := math.Float32frombits(0)
    res_4 := math.Float32frombits(223)

    // Displaying the result
    fmt.Println("Result 1: ", res_1)
    fmt.Println("Result 2: ", res_2)
    fmt.Println("Result 3: ", res_3)
    fmt.Println("Result 4: ", res_4)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  3e-45
Result 2:  1e-45
Result 3:  0
Result 4:  3.12e-43

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
    // Using Float32frombits() function
    nvalue_1 := math.Float32frombits(3)
    nvalue_2 := math.Float32frombits(50)

    // Sum of the given values
    res := nvalue_1 + nvalue_2
    fmt.Println("Result 1: ", nvalue_1)
    fmt.Println("Result 2: ", nvalue_2)
    fmt.Println("Sum of Result 1 and Result 2: ", res)

}
```

发帖主题：Re：Колибри0.7.0

```go
Result 1:  4e-45
Result 2:  7e-44
Sum of Result 1 and Result 2:  7.4e-44

```