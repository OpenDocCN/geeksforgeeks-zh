# 位。Sub32()函数在 Golang 中的应用举例

> 原文:[https://www . geesforgeks . org/bits-sub 32-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-sub32-function-in-golang-with-examples/)

**位。利用 Golang 中的 Sub32()** 函数求 a、b、借位的差，即 diff = a–b–借位。这里借位必须是 0 或 1；否则，行为是未定义的。要访问这个函数，需要在程序中导入数学/位包。在任何情况下，*借贷输出*的返回值总是 0 或 1。

**语法:**

```go
func Sub32(a, b, borrow uint32) (diff, borrowOut uint32)

```

**参数:**该函数取 uint32 类型的三个参数，即 a、b、借用。借用参数的值为 1 或 0。

**返回值:**该函数返回 uint32 类型的两个值，即 diff 和 borrowOut。这里 diff 包含 a–b–借位的结果，借位不是 1 就是 0。

**例 1:**

```go
// Golang program to illustrate bits.Sub32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding diff and borrowOu
    // of the specified numbers
    // Using Sub32() function
    nvalue_1, borrowOut := bits.Sub32(13, 8, 1)
    fmt.Println("Diff:", nvalue_1)
    fmt.Println("BorrowOut :", borrowOut)

}
```

**输出:**

```go
Diff: 4
BorrowOut : 0

```

**例 2:** 这里可以看到，结果并不像我们把借的值取为 3 那样例外。因此，如果我们采用 1 和 0 以外的借用输入，那么行为将是未定义的。

```go
// Golang program to illustrate bits.Sub32() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding diff and borrowOut
    // of the specified numbers
    // Using Sub32() function

    var a, b, borrow uint32 = 4, 15, 3
    Diff, borrowOut := bits.Sub32(a, b, borrow)
    fmt.Println("Number 1:", a)
    fmt.Println("Number 2:", b)
    fmt.Println("Borrow :", borrow)
    fmt.Println("Diff:", Diff)
    fmt.Println("BorrowOut :", borrowOut)

}
```

**输出:**

```go
Number 1: 4
Number 2: 15
Borrow : 3
Diff: 4294967282
BorrowOut : 1

```