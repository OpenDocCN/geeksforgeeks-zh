# 在 Go 语言中使用 Recover

> 原文: [https://www.geeksforgeeks.org/recover-in-golang/](https://www.geeksforgeeks.org/recover-in-golang/)

就像 [Java](https://www.geeksforgeeks.org/java/)、[C#](https://www.geeksforgeeks.org/csharp-programming-language/) 等语言中的 `try/catch` 块一样，在 Go 语言中也有类似的机制用于捕捉异常。`recover` 函数用于处理 `panic`（死机）。这是一个内置函数，在 Go 语言的内置包中定义。这个功能的主要用途是重新获得发生 `panic` 的 goroutine 的控制权。或者换句话说，它处理 [goroutine](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/) 的 `panic` 行为。

## 语法

```go
func recover() interface{}
```

## 要点

*   `recover` 函数总是在延迟函数（通过 `defer` 声明的函数）内部调用，而不是在普通函数中调用。如果在普通函数内部或延迟函数外部调用 `recover` 函数，则它不会停止 `panic` 序列，如示例 1 所示。因此，总是在延迟函数中调用 `recover` 函数，因为如果程序发生 `panic`，延迟函数仍会执行，`recover` 函数通过恢复 goroutine 的正常执行来停止 `panic` 序列，并检索传递给 `panic` 调用的错误值，如示例 2 所示。
*   只有在发生 `panic` 的同一个 goroutine 中调用，`recover` 函数才有效。如果您在不同的 goroutine 中调用它，那么它将不会像示例 3 中所示的那样工作。
*   如果你想获取堆栈跟踪信息，那么可以使用在 `debug` 包下定义的 `PrintStack` 函数。

## 示例 1

```go
// Go program which illustrates
// the concept of recover
package main

import "fmt"

// This function is created to handle
// the panic occurs in entry function
// but it does not handle the panic 
// occurred in the entry function
// because it called in the normal
// function
func handlepanic() {

    if a := recover(); a != nil {
        fmt.Println("RECOVER", a)
    }
}

// Function
func entry(lang *string, aname *string) {

    // Normal function
    handlepanic()

    // When the value of lang
    // is nil it will panic
    if lang == nil {
        panic("Error: Language cannot be nil")
    }

    // When the value of aname
    // is nil it will panic
    if aname == nil {
        panic("Error: Author name cannot be nil")
    }

    fmt.Printf("Author Language: %s \n Author Name: %s\n", *lang, *aname)
    fmt.Printf("Return successfully from the entry function")
}

// Main function
func main() {

    A_lang := "GO Language"
    entry(&A_lang, nil)
    fmt.Printf("Return successfully from the main function")
}
```

### 输出

```go
panic: Error: Author name cannot be nil

goroutine 1 [running]:
main.entry(0x41a788, 0x0)
    /tmp/sandbox777592252/prog.go:35 +0x180
main.main()
    /tmp/sandbox777592252/prog.go:46 +0x40

```

## 示例 2

```go
// Go program which illustrates
// the concept of recover
package main

import (
    "fmt"
)

// This function handles the panic
// occur in entry function
// with the help of the recover function
func handlepanic() {

    if a := recover(); a != nil {

        fmt.Println("RECOVER", a)
    }
}

// Function
func entry(lang *string, aname *string) {

    // Deferred function
    defer handlepanic()

    // When the value of lang
    // is nil it will panic
    if lang == nil {

        panic("Error: Language cannot be nil")
    }

    // When the value of aname
    // is nil it will panic
    if aname == nil {
        panic("Error: Author name cannot be nil")
    }
    fmt.Printf("Author Language: %s \n Author Name: %s\n", *lang, *aname)
    fmt.Printf("Return successfully from the entry function")
}

// Main function
func main() {

    A_lang := "GO Language"
    entry(&A_lang, nil)
    fmt.Printf("Return successfully from the main function")
}
```

### 输出

```go
RECOVER Error: Author name cannot be nil
Return successfully from the main function

```

## 示例 3

```go
// Go program which illustrates
// recover in a goroutine
package main

import (
    "fmt"
    "time"
)

// For recovery
func handlepanic() {
    if a := recover(); a != nil {
        fmt.Println("RECOVER", a)
    }
}

/* Here, this panic is not 
   handled by the recover 
   function because of the 
   recover function is not 
   called in the same 
   goroutine in which the 
   panic occurs */

// Function 1
func myfun1() {

    defer handlepanic()
    fmt.Println("Welcome to Function 1")
    go myfun2()
    time.Sleep(10 * time.Second)
}

// Function 2
func myfun2() {

    fmt.Println("Welcome to Function 2")
    panic("Panicked!!")
}

// Main function
func main() {

    myfun1()
    fmt.Println("Return successfully from the main function")
}
```

### 输出

```go
Welcome to Function 1
Welcome to Function 2
panic: Panicked!!

goroutine 6 [running]:
main.myfun2()
    /tmp/sandbox157568972/prog.go:31 +0xa0
created by main.myfun1
    /tmp/sandbox157568972/prog.go:24 +0xc0

```