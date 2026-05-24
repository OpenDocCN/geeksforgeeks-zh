# 比较戈朗的指针

> 原文:[https://www.geeksforgeeks.org/comparing-pointers-in-golang/](https://www.geeksforgeeks.org/comparing-pointers-in-golang/)

[指针](https://www.geeksforgeeks.org/pointers-in-golang/)在 Go 编程语言或 Golang 中是一个变量，用来存储另一个变量的内存地址。Golang 中的指针也被称为特殊变量。变量用于在系统的特定内存地址存储一些数据。内存地址总是以十六进制格式出现(从 0x 开始，如 0xFFAAF 等)。).
在围棋语言中，你可以比较两个指针。两个指针值只有在指向内存中的相同值或为零时才相等。您可以借助 **==** 和**对指针进行比较！=**Go 语言提供的运算符:

**1。==运算符:**如果两个指针都指向同一个变量，则该运算符返回 true。或者如果两个指针都指向不同的变量，则返回 false。

**语法:**

```go
pointer_1 == pointer_2
```

**示例:**

```go
// Go program to illustrate the
// concept of comparing two pointers
package main

import "fmt"

func main() {

    val1 := 2345
    val2 := 567

    // Creating and initializing pointers
    var p1 *int
    p1 = &val1
    p2 := &val2
    p3 := &val1

    // Comparing pointers 
    // with each other
    // Using == operator
    res1 := &p1 == &p2
    fmt.Println("Is p1 pointer is equal to p2 pointer: ", res1)

    res2 := p1 == p2
    fmt.Println("Is p1 pointer is equal to p2 pointer: ", res2)

    res3 := p1 == p3
    fmt.Println("Is p1 pointer is equal to p3 pointer: ", res3)

    res4 := p2 == p3
    fmt.Println("Is p2 pointer is equal to p3 pointer: ", res4)

    res5 := &p3 == &p1
    fmt.Println("Is p3 pointer is equal to p1 pointer: ", res5)
}
```

**输出:**

```go
Is p1 pointer is equal to p2 pointer:  false
Is p1 pointer is equal to p2 pointer:  false
Is p1 pointer is equal to p3 pointer:  true
Is p2 pointer is equal to p3 pointer:  false
Is p3 pointer is equal to p1 pointer:  false

```

**2。！=运算符:**如果两个指针都指向同一个变量，则该运算符返回 false。或者如果两个指针都指向不同的变量，则返回 true。

**语法:**

```go
pointer_1 != pointer_2
```

**示例:**

```go
// Go program to illustrate the 
// concept of comparing two pointers
package main

import "fmt"

func main() {

    val1 := 2345
    val2 := 567

    // Creating and initializing pointers
    var p1 *int
    p1 = &val1
    p2 := &val2
    p3 := &val1

    // Comparing pointers
    // with each other
    // Using != operator
    res1 := &p1 != &p2
    fmt.Println("Is p1 pointer not equal to p2 pointer: ", res1)

    res2 := p1 != p2
    fmt.Println("Is p1 pointer not equal to p2 pointer: ", res2)

    res3 := p1 != p3
    fmt.Println("Is p1 pointer not equal to p3 pointer: ", res3)

    res4 := p2 != p3
    fmt.Println("Is p2 pointer not equal to p3 pointer: ", res4)

    res5 := &p3 != &p1
    fmt.Println("Is p3 pointer not equal to p1 pointer: ", res5)
}
```

**输出:**

```go
Is p1 pointer not equal to p2 pointer:  true
Is p1 pointer not equal to p2 pointer:  true
Is p1 pointer not equal to p3 pointer:  false
Is p2 pointer not equal to p3 pointer:  true
Is p3 pointer not equal to p1 pointer:  true

```