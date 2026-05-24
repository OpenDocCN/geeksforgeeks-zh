# 位。带示例的 Golang 中的 LeadingZeros8()函数

> 原文:[https://www . geesforgeks . org/bits-leading zero S8-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-leadingzeros8-function-in-golang-with-examples/)

**位。Golang 中的 LeadingZeros8()函数**用于查找给定数字中的前导零位数。如果给定的数字等于零，那么这个方法将返回 8。要访问这个函数，需要在程序中导入数学/位包。

> **语法:**
> 
> ```go
> func LeadingZeros8(x uint8) int
> 
> ```
> 
> **参数:**该函数取 uint8 类型的一个参数，即 x。
> 
> **返回值:**该函数返回 x 中前导零位的总数。

**例 1:**

```go
// Golang program to illustrate
// bits.LeadingZeros8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using LeadingZeros8() function
    x := bits.LeadingZeros8(4)
    fmt.Println("Total number of leading zero bits: ", x)

}
```

**输出:**

```go
Total number of leading zero bits:  5

```

**例 2:**

```go
// Golang program to illustrate
// bits.LeadingZeros8() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Using LeadingZeros8() function
    x := bits.LeadingZeros8(0)
    fmt.Println("Total number of leading zero bits: ", x)

}
```

**输出:**

```go
Total number of leading zero bits:  8

```