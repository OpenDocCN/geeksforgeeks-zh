# 使用defer关键字的Golang程序

> 原文：[https://www.geeksforgeeks.org/golang-program-that-uses-defer-keyword/](https://www.geeksforgeeks.org/golang-program-that-uses-defer-keyword/)

Go语言中`defer`关键字的主要用途是清理打开的文件、网络连接、数据库句柄等使用的资源。这有助于通过保持关闭函数/文件的调用更接近打开语句的调用来减少出错的机会。后面跟有`defer`关键字的语句被放在堆栈上，最后，它们按照后进先出（LIFO）的顺序被调用。

**示例：**

```go
package main

import "fmt"

func main() {
    defer fmt.Println("First")
    defer fmt.Println("Second")
    fmt.Println("Last")
}
```

**输出：**

```go
Last
Second
First
```

在这里，您可以看到语句是根据LIFO顺序打印的。但是，这并不是`defer`的主要目的，所以我们将在程序中了解`defer`关键字的主要用途。

**实际应用场景：**

```go
func write(fileName string, text string) error {
    file, err := os.Create(fileName)
    if err != nil {
        return err
    }
    _, err = io.WriteString(file, text)
    if err != nil {
        return err
    }
    file.Close()
    return nil
}
```

在此函数中，如果`io.WriteString`失败，那么程序将返回错误`err`，并且它将无法关闭文件，这将导致资源浪费，因此这里的`defer`将是有用的。

```go
func write(fileName string, text string) error {
    file, err := os.Create(fileName)
    if err != nil {
        return err
    }

    // This statement will surely run at the end no 
    // matter what the program goes through.
    defer file.Close()

    _, err = io.WriteString(file, text)
    if err != nil {
        return err
    }

    return file.Close()
}
```

在这个程序中，语句`defer file.Close()`将在函数结束时运行，如果程序中有错误，那么它将能够关闭程序中较早打开的文件，从而节省资源。以下是相同的完整程序。

**完整程序示例：**

```go
package main

import (
    "io"
    "log"
    "os"
)

func main() {
    if err := write("readme.txt", "This is a readme file"); err != nil {
        log.Fatal("failed to write file:", err)
    }
}

func write(fileName string, text string) error {
    file, err := os.Create(fileName)
    if err != nil {
        return err
    }
    defer file.Close()
    _, err = io.WriteString(file, text)
    if err != nil {
        return err
    }

    return file.Close()
}
```