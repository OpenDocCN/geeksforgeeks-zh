# bits.LeadingZeros32() 函数示例（Golang）

> 原文：[https://www.geeksforgeeks.org/bits-leadingzeros32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-leadingzeros32-function-in-golang-with-examples/)

`bits.LeadingZeros32()` 函数用于计算给定数字中前导零位的个数。如果给定的数字等于零，那么这个函数将返回 32。要访问这个函数，需要在程序中导入 `math/bits` 包。

> **语法：**
> ```go
> func LeadingZeros32(x uint32) int
> ```
> **参数：** 该函数取 `uint32` 类型的一个参数，即 `x`。
> **返回值：** 该函数返回 `x` 中前导零位的总数。

**例 1：**
```go
// Golang program to illustrate
// bits.LeadingZeros32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using LeadingZeros32() function
    x := bits.LeadingZeros32(9)
    fmt.Println("Total number of leading zero bits: ", x)

}
```
**输出：**
```go
Total number of leading zero bits:  28
```

**例 2：**
```go
// Golang program to illustrate
// bits.LeadingZeros32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using LeadingZeros32() function
    x := bits.LeadingZeros32(0)
    fmt.Println("Total number of leading zero bits: ", x)

}
```
**输出：**
```go
Total number of leading zero bits:  32
```