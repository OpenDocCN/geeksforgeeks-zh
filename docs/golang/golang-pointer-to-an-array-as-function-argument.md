# 指向数组的指针作为函数参数

> 原文:[https://www . geeksforgeeks . org/golang-指针指向数组作为函数参数/](https://www.geeksforgeeks.org/golang-pointer-to-an-array-as-function-argument/)

**先决条件:[格朗指针](https://www.geeksforgeeks.org/pointers-in-golang/)**

[Go](https://www.geeksforgeeks.org/go-programming-language-introduction/) 编程语言或 Golang 中的指针是一个变量，用于存储另一个[变量](https://www.geeksforgeeks.org/go-variables/)的内存地址。而[数组](https://www.geeksforgeeks.org/arrays-in-go/)是一个固定长度的序列，用于在内存中存储同类元素。

您可以使用指向数组的指针，并将该指针作为参数传递给函数。为了理解这个概念，让我们举个例子。在下面的程序中，我们取了一个有 5 个元素的指针数组 **arr** 。我们想用一个函数更新这个数组。意味着修改函数内部的数组(这里的数组是 *{78，89，45，56，14}* )，它将反映在调用者身上。所以这里我们把函数**更新数组**作为参数类型，它有一个指向数组的指针。使用 **updatearray( & arr)** 行代码，我们传递数组的地址。内部函数 *(*funarr)[4] = 750* 或 *funarr[4] = 750* 代码行正在使用解引用概念为数组赋值，新值将反映在原始数组中。最后，程序会给出输出*【78 89 45 56 750】*。

```go
// Golang program to pass a pointer to an
// array as an argument to the function
package main

import "fmt"

// taking a function
func updatearray(funarr *[5]int) {

    // updating the array value
    // at specified index
    (*funarr)[4] = 750

    // you can also write 
    // the above line of code
    // funarr[4] = 750
}

// Main Function
func main() {

    // Taking an pointer to an array
    arr := [5]int{78, 89, 45, 56, 14}

    // passing pointer to an array
    // to function updatearray
    updatearray(&arr)

    // array after updating
    fmt.Println(arr)
}
```

**输出:**

```go
[78 89 45 56 750]

```

**注意:**在 Golang 中，不建议使用指向数组的指针作为函数的参数，因为代码变得难以阅读。此外，这也被认为不是实现这一概念的好方法。为了实现这一点，您可以使用切片而不是传递指针。

**示例:**

```go
// Golang program to illustrate the
// concept of passing a pointer to an
// array as an argument to the function
// using a slice
package main

import "fmt"

// taking a function
func updateslice(funarr []int) {

    // updating the value
    // at specified index
    funarr[4] = 750
}

// Main Function
func main() {

    // Taking an slice
    s := [5]int{78, 89, 45, 56, 14}

    // passing slice to the
    // function updateslice
    updateslice(s[:])

    // displaying the result
    fmt.Println(s)
}
```

**输出:**

```go
[78 89 45 56 750]

```