# 位。Golang 中的 Add32()函数及示例

> 原文:[https://www . geesforgeks . org/bits-add32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-add32-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **Add32()函数**，用来求 a，b，进位的和，即和= a + b +进位。这里进位的值必须是 0 或 1，否则，行为是未定义的。要访问 Add32()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

> **语法:**
> 
> ```go
> func Add32(a, b, carry uint32) (sum, carryout uint32)
> ```
> 
> **参数:**该函数取 uint32 类型的三个参数，即 a、b、进位。进位参数的值是 1 或 0。
> 
> **返回值:**该函数返回 uint32 类型的两个值，即求和和进位。这里 sum 包含 a + b +进位的结果，进位不是 1 就是 0。

**例 1:**

```go
// Golang program to illustrate bits.Add32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding sum and carry 
    // of the specified numbers
    // Using Add32() function
    nvalue_1, carry := bits.Add32(20, 12, 1)
    fmt.Println("Sum:", nvalue_1)
    fmt.Println("Carry:", carry)

}
```

**输出:**

```go
Sum: 33
Carry: 0

```

**例 2:**

```go
// Golang program to illustrate bits.Add32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding sum and carry 
    // of the specified numbers
    // Using Add32() function
    var a, b, carry uint32 = 31, 34, 0
    sum, carryout := bits.Add32(a, b, carry)
    fmt.Println("Number 1:", a)
    fmt.Println("Number 2:", b)
    fmt.Println("Carry:", carry)
    fmt.Println("Sum:", sum)
    fmt.Println("Carry:", carryout)

}
```

**输出:**

```go
Number 1: 31
Number 2: 34
Carry: 0
Sum: 65
Carry: 0

```