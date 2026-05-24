# 位。带示例的 Golang 中的 LeadingZeros16()函数

> 原文:[https://www . geesforgeks . org/bits-leading zero s16-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-leadingzeros16-function-in-golang-with-examples/)

**位。Golang 中的 LeadingZeros16()函数**用于查找给定数字中的前导零位数。如果给定的数字等于零，那么这个方法将返回 16。要访问这个函数，需要在程序中导入数学/位包。

> **语法:**
> 
> ```go
> func LeadingZeros16(x uint16) int
> 
> ```
> 
> **参数:**该函数取 uint16 类型的一个参数，即 x。
> 
> **返回值:**该函数返回 x 中前导零位的总数。

**例 1:**

```go
// Golang program to illustrate
// bits.LeadingZeros16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using LeadingZeros16() function
    x := bits.LeadingZeros16(3)
    fmt.Println("Total number of leading zero bits: ", x)

}
```

**输出:**

```go
Total number of leading zero bits:  14

```

**例 2:**

```go
// Golang program to illustrate
// bits.LeadingZeros16() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using LeadingZeros16() function
    x := bits.LeadingZeros16(0)
    fmt.Println("Total number of leading zero bits: ", x)

}
```

**输出:**

```go
Total number of leading zero bits:  16

```