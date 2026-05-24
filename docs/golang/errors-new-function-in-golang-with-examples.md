# 错误。Golang 中的新()函数及示例

> 原文:[https://www . geesforgeks . org/errors-new-function-in-golang-with-examples/](https://www.geeksforgeeks.org/errors-new-function-in-golang-with-examples/)

Golang 中的错误包用于实现操作错误的函数。**错误。New()** 函数返回一个格式类似给定文本的错误。如果内容无法区分，那么对 New 的每个调用都会返回不同的错误值。

**语法:**

```go
func New(text string) error
```

它返回一个错误。

**例 1:**

```go
// Golang program to illustrate
// the errors.new() function 
package main

import (
    "errors"
    "fmt"
)
// Main function
func main() {
    err := errors.New("Sample Error")
    if err != nil {
        fmt.Print(err)
    }
}
```

**输出:**

```go
Sample Error
```

**例 2:**

```go
// Golang program to illustrate
// the errors.new() function
package main

import (
    "errors"
    "fmt"
)

// Main function
func main() {
    err := errors.New("It Says Error!")
    if err != nil {
        fmt.Print(err)
    }
}
```

**输出:**

```go
It Says Error!
```