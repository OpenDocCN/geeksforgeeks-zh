# 在戈朗恢复

> 原文:[https://www.geeksforgeeks.org/recover-in-golang/](https://www.geeksforgeeks.org/recover-in-golang/)

就像 [Java](https://www.geeksforgeeks.org/java/) 、 [C#](https://www.geeksforgeeks.org/csharp-programming-language/) 等语言中异常中的 try/catch 块一样。在 Go 语言中类似用于捕捉异常，recover 函数用于处理死机。这是一个内置函数，在 Go 语言的内置包中定义。这个功能的主要用途是重新控制惊慌失措的戈鲁丁。或者换句话说，它处理[戈罗廷](https://www.geeksforgeeks.org/goroutines-concurrency-in-golang/)的恐慌行为。

**语法:**

```go
func recover() interface{}
```

**要点:**

*   恢复函数总是在延迟函数内部调用，而不是在正常函数中调用。如果在正常函数内部或延迟函数外部调用恢复函数，则恢复函数不会停止如示例 1 所示的恐慌序列。因此，总是在延迟函数中调用 recover 函数，因为如果程序死机，延迟函数不会停止执行，所以 recover 函数通过简单地恢复 goroutine 的正常执行来停止死机序列，并检索传递给死机调用的错误值，如示例 2 所示。
*   只有在发生死机的同一个 goroutine 中调用，Recover 函数才有效。如果您在不同的 goroutine 中调用它，那么它将不会像示例 3 中所示的那样工作。
*   如果你想找到堆栈跟踪，那么使用在调试包下定义的打印堆栈函数。

**例 1:**

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

**输出:**

```go
panic: Error: Author name cannot be nil

goroutine 1 [running]:
main.entry(0x41a788, 0x0)
    /tmp/sandbox777592252/prog.go:35 +0x180
main.main()
    /tmp/sandbox777592252/prog.go:46 +0x40

```

**例 2:**

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

**输出:**

```go
RECOVER Error: Author name cannot be nil
Return successfully from the main function

```

**例 3:**

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

**输出:**

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