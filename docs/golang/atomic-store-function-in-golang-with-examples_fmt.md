# 原子：在 Golang 中 `Store()` 函数并举例

> 原文：[https://www.geeksforgeeks.org/atomic-store-function-in-golang-with-examples/](https://www.geeksforgeeks.org/atomic-store-function-in-golang-with-examples/)

在 Go 语言中，`atomic` 包提供较低级别的原子内存，这有助于实现同步算法。Go 语言中的 `Store()` 函数用于将 `Value` 的值设置为 `x`（即接口）。
对于所述 `Value` 调用 `Store` 方法的所有调用都应该使用相同具体类型的值。而且，矛盾类型的 `Store` 会引发 `panic`。这个函数是在 `atomic` 包下定义的。在这里，你需要导入 `sync/atomic` 包才能使用这些功能。

## 语法：

```go
func (v *Value) Store(x interface{})
```

这里 `v` 为任意类型的值，`x` 为存储方法输出结果类型的接口。

## 注意：

`(*Value)` 是指向一个 `Value` 类型的指针。`sync/atomic` 标准包中提供的 `Value` 类型用于原子存储和加载任何类型的值。

## 返回值：

存储提供的值，需要时可以加载。

## 例 1：

```go
// Program to illustrate the usage of
// Store function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "fmt"
    "sync/atomic"
)

// Main function
func main() {

// Defining a struct type L
    type L struct{ x, y, z int }

// Defining a variable to assign
    // values to the struct type L
    var r1 = L{9, 10, 11}

// Defining Value type to store
    // values of any type
    var V atomic.Value

// Calling Store function
    V.Store(r1)

// Printed if the value stated is stored
    fmt.Println("Any type of value is stored!")
}
```

## 输出：

```go
Any type of value is stored!
```

在上面的例子中，我们使用了 `Value` 类型来存储任何类型的值。这些值存储在 `r1`，即所述的接口。

## 例 2：

```go
// Program to illustrate the usage of
// Store function in Golang

// Including main package
package main

// importing fmt and sync/atomic
import (
    "sync/atomic"
)

// Main function
func main() {

// Defining a struct type L
    type L struct{ x, y, z int }

// Defining a variable to assign
    // values to the struct type L
    var r1 = L{9, 10, 11}

// Defining Value type to store
    // values of any type
    var V atomic.Value

// Calling Store function
    V.Store(r1)

// Storing value of
    // different concrete type
    V.Store("GeeksforGeeks")
}
```

## 输出：

```go
panic: sync/atomic: store of inconsistently typed value into Value

goroutine 1 [running]:
sync/atomic.(*Value).Store(0x40c018, 0x99a40, 0xb23e8, 0x40e010)
    /usr/local/go/src/sync/atomic/value.go:77 +0x160
main.main()
    /tmp/sandbox206117237/prog.go:31 +0xc0
```

这里，上面存储的值是不同的具体类型，因此引发了 `panic`。