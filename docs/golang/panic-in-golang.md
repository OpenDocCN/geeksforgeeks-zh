# 戈朗恐慌

> 原文:[https://www.geeksforgeeks.org/panic-in-golang/](https://www.geeksforgeeks.org/panic-in-golang/)

在 Go 语言中，恐慌就像一个例外，它也在运行时出现。或者换句话说，恐慌意味着在你的 Go 程序中出现了一个意外情况，由于这个情况，你的程序的执行被终止了。有时，当出现某些特定情况时，如越界数组访问等，运行时会出现死机。如示例 1 所示，或者有时是程序员故意抛出的，以借助示例 2 所示的*恐慌()*函数来处理 Go 程序中的最坏情况。
恐慌函数是内置函数，在 Go 语言的内置包中定义。该函数终止控制流并开始恐慌。

**语法:**

```go
func panic(v interface{})
```

它可以接受任何类型的参数。当 Go 程序中出现死机时，程序会在运行时终止，并在输出屏幕中显示一条错误消息和堆栈跟踪，直到出现死机为止。通常，在 go 语言中，当程序出现死机时，程序不会立即终止，而是在 Go 完成该程序的所有挂起工作时终止。
**例如**，假设一个函数 A 调用了死机，那么函数 A 的执行就停止了，如果在 A 中有任何延迟的函数可用，那么在函数 A 返回到它的调用者并且调用者 A 的行为类似于对死机的调用之后，它们就正常执行了。这个过程一直持续到返回当前 goroutine 中的所有函数，之后程序崩溃，如示例 3 所示。

**例 1:**

```go
// Simple Go program which illustrates
// the concept of panic
package main

import "fmt"

// Main function
func main() {

    // Creating an array of string type
    // Using var keyword
    var myarr [3]string

    // Elements are assigned
    // using an index
    myarr[0] = "GFG"
    myarr[1] = "GeeksforGeeks"
    myarr[2] = "Geek"

    // Accessing the elements
    // of the array
    // Using index value
    fmt.Println("Elements of Array:")
    fmt.Println("Element 1: ", myarr[0])

    // Program panics because
    // the size of the array is
    // 3 and we try to access
    // index 5 which is not 
    // available in the current array,
    // So, it gives an runtime error
    fmt.Println("Element 2: ", myarr[5])

}
```

**输出:**

```go
./prog.go:32:34: invalid array index 5 (out of bounds for 3-element array)
```

**例 2:**

```go
// Go program which illustrates 
// how to create your own panic
// Using panic function
package main

import "fmt"

// Function
func entry(lang *string, aname *string) {

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

    // When the values of the lang and aname 
    // are non-nil values it will print 
    // normal output
    fmt.Printf("Author Language: %s \n Author Name: %s\n", *lang, *aname)
}

// Main function
func main() {

    A_lang := "GO Language"

    // Here in entry function, we pass 
    // a non-nil and nil values
    // Due to nil value this method panics
    entry(&A_lang, nil)
}
```

**输出:**

```go
panic: Error: Author name cannot be nil

goroutine 1 [running]:
main.entry(0x41a788, 0x0)
    /tmp/sandbox108627012/prog.go:20 +0x140
main.main()
    /tmp/sandbox108627012/prog.go:37 +0x40

```

**例 3:**

```go
// Go program which illustrates the
// concept of Defer while panicking
package main

import (
    "fmt"
)

// Function
func entry(lang *string, aname *string) {

    // Defer statement
    defer fmt.Println("Defer statement in the entry function")

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

    // When the values of the lang and aname
    // are non-nil values it will 
    // print normal output
    fmt.Printf("Author Language: %s \n Author Name: %s\n", *lang, *aname)
}

// Main function
func main() {

    A_lang := "GO Language"

    // Defer statement
    defer fmt.Println("Defer statement in the Main function")

    // Here in entry function, we pass
    // one non-nil and one-nil value
    // Due to nil value this method panics
    entry(&A_lang, nil)
}
```

**输出:**

```go
Defer statement in the entry function
Defer statement in the Main function
panic: Error: Author name cannot be nil

goroutine 1 [running]:
main.entry(0x41a780, 0x0)
    /tmp/sandbox121565297/prog.go:24 +0x220
main.main()
    /tmp/sandbox121565297/prog.go:44 +0xa0

```

**注意:**即使程序死机，Defer 语句或函数始终运行。

**恐慌的用法:**

*   当程序无法继续执行时，您可以对不可恢复的错误使用死机。
*   如果您希望程序中出现特定条件的错误，也可以使用死机。