# bits.Sub64() 函数在 Golang 中的应用举例

> 原文：[https://www.geeksforgeeks.org/bits-sub64-function-in-golang-with-examples/](https://www.geeksforgeeks.org/bits-sub64-function-in-golang-with-examples/)

`bits.Sub64()` 函数用于计算 `a`、`b` 和 `borrow` 的差值，即 `diff = a - b - borrow`。这里 `borrow` 必须是 0 或 1；否则，行为是未定义的。要访问这个函数，需要在程序中导入 `math/bits` 包。在任何情况下，`borrowOut` 的返回值总是 0 或 1。

## 语法

```go
func Sub64(a, b, borrow uint64) (diff, borrowOut uint64)
```

## 参数

该函数取 `uint64` 类型的三个参数，即 `a`、`b`、`borrow`。`borrow` 参数的值为 1 或 0。

## 返回值

该函数返回 `uint64` 类型的两个值，即 `diff` 和 `borrowOut`。这里 `diff` 包含 `a - b - borrow` 的结果，`borrowOut` 不是 1 就是 0。

## 例 1

```go
// Golang program to illustrate bits.Sub64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding diff and borrowOut
    // of the specified numbers
    // Using Sub64() function
    nvalue_1, borrowOut := bits.Sub64(11, 5, 0)
    fmt.Println("Diff:", nvalue_1)
    fmt.Println("BorrowOut :", borrowOut)

}
```

**输出：**

```go
Diff: 6
BorrowOut : 0
```

## 例 2

这里可以看到，结果并不像我们把借的值取为 7 那样例外。因此，如果我们采用 1 和 0 以外的借用输入，那么行为将是未定义的。

```go
// Golang program to illustrate bits.Sub64() Function
package main

import (
    "fmt"
    "math/bits"
)

// Main function
func main() {

    // Finding diff and borrowOut
    // of the specified numbers
    // Using Sub64() function

    var a, b, borrow uint64 = 12, 87, 7
    Diff, borrowOut := bits.Sub64(a, b, borrow)
    fmt.Println("Number 1:", a)
    fmt.Println("Number 2:", b)
    fmt.Println("Borrow :", borrow)
    fmt.Println("Diff:", Diff)
    fmt.Println("BorrowOut :", borrowOut)

}
```

**输出：**

```go
Number 1: 12
Number 2: 87
Borrow : 7
Diff: 18446744073709551540
BorrowOut : 1
```