# 如何获取 Golang 当前工作目录？

> 原文:[https://www . geesforgeks . org/如何获取当前工作目录 in-golang/](https://www.geeksforgeeks.org/how-to-get-the-current-working-directory-in-golang/)

**Getwd 函数**用于获取 Golang 中的当前工作目录，函数返回根路径名，如果可以通过多条路径到达当前目录，函数可以返回其中任意一条。

**语法:**

```go
func Getwd()(dir string, err error)
```

func 返回两个东西:目录和错误，如果没有错误，它返回零。

```go
// Golang code for printing
// current working directory

package main

import (
    "fmt"
    "os"
)

func main() {

    // using the function
    mydir, err := os.Getwd()
    if err != nil {
        fmt.Println(err)
    }
    fmt.Println(mydir)
}
```

**输出:**

```go
users/home/desktop
```

您可能会在在线编译器上获得不同的输出。为了更好地理解，请使用离线编译器。