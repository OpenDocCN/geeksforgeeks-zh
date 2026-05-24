# 位。Golang 中的 Sub()函数示例

> 原文:[https://www . geesforgeks . org/bits-sub-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-sub-function-in-golang-with-examples/)

**位。sub()**Golang 中的函数用来求 a、b、借位的差，即 diff = a–b–借位。这里借位必须是 0 或 1；否则，行为是未定义的。要访问这个函数，需要在程序中导入数学/位包。在任何情况下，*借贷输出*的返回值总是 0 或 1。

**语法:**

```go
func Sub(a, b, borrow uint) (diff, borrowOut uint)

```

**参数:**该函数取 uint 类型的三个参数，即 a、b、借用。借用参数的值为 1 或 0

**返回值:**该函数返回 uint 类型的两个值，即 diff 和 borrowOut。这里 diff 包含 a–b–借位的结果，借位不是 1 就是 0。

**例 1:**

```go
// Golang program to illustrate bits.Sub() Function 
package main 

import ( 
    "fmt"
    "math/bits"
) 

// Main function 
func main() { 

    // Finding diff and borrowOu 
    // of the specified numbers 
    // Using Sub() function 
    nvalue_1, borrowOut := bits.Sub(4, 3, 0) 
    fmt.Println("Diff:", nvalue_1) 
    fmt.Println("BorrowOut :", borrowOut ) 

} 
```

**输出:**

```go
Diff: 1
BorrowOut : 0

```

**例 2:**

```go
// Golang program to illustrate bits.Sub() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding diff and borrowOut
    // of the specified numbers
    // Using Sub() function

    var a, b, borrow uint = 10, 5, 1
    Diff, borrowOut := bits.Sub(a, b, borrow)
    fmt.Println("Number 1:", a)
    fmt.Println("Number 2:", b)
    fmt.Println("Borrow :", borrow)
    fmt.Println("Diff:", Diff)
    fmt.Println("BorrowOut :", borrowOut)

}
```

**输出:**

```go
Number 1: 10
Number 2: 5
Borrow : 1
Diff: 4
BorrowOut : 0

```