# 位。在 Golang 中添加()函数并举例

> 原文:[https://www . geesforgeks . org/bits-add-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-add-function-in-golang-with-examples/)

Go 语言在 bits 包的帮助下，为 bits 提供内置支持，以实现预声明的无符号整数类型的位计数和操作功能。这个包提供了 **Add()函数**，用来求 a，b，进位的和，即和= a + b +进位。这里进位的值必须是 0 或 1，否则，行为是未定义的。要访问 Add()函数，您需要借助 import 关键字在程序中添加一个数学/位包。

**语法:**

```go
func Add(a, b, carry uint) (sum, carryout unit)
```

**参数:**该函数取 uint 类型的三个参数，即 a、b、进位。进位参数的值是 1 或 0。

**返回值:**该函数返回两个 uint 类型的值，即求和和进位。这里 sum 包含 a + b +进位的结果，进位不是 1 就是 0。

**例 1:**

```go
// Golang program to illustrate bits.Add() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding sum and carry 
    // of the specified numbers
    // Using Add() function
    nvalue_1, carry := bits.Add(2, 3, 0)
    fmt.Println("Sum:", nvalue_1)
    fmt.Println("Carry:", carry)

}
```

**输出:**

```go
Sum: 5
Carry: 0

```

**例 2:**

```go
// Golang program to illustrate bits.Add() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding sum and carry 
    // of the specified numbers
    // Using Add() function
    var a, b, carry uint = 4, 5, 1
    sum, carryout := bits.Add(a, b, carry)
    fmt.Println("Number 1:", a)
    fmt.Println("Number 2:", b)
    fmt.Println("Carry:", carry)
    fmt.Println("Sum:", sum)
    fmt.Println("Carry:", carryout)

}
```

**输出:**

```go
Number 1: 4
Number 2: 5
Carry: 1
Sum: 10
Carry: 0

```