# 如何在 Golang 中将切片传递给函数？

> 原文:[https://www . geesforgeks . org/如何将切片传递给函数 in-golang/](https://www.geeksforgeeks.org/how-to-pass-a-slice-to-function-in-golang/)

[切片](https://www.geeksforgeeks.org/slices-in-golang/)是存储相似类型元素的变长序列，不允许在同一个切片中存储不同类型的元素。它就像一个有索引值和长度的[数组](https://www.geeksforgeeks.org/arrays-in-go/)，但是切片的大小被调整，它们不像数组一样是固定大小的。在 Go 语言中，您可以将一个切片传递给一个[函数](https://www.geeksforgeeks.org/functions-in-go-language/)，这意味着该函数将获得该切片的副本。
切片通过值与切片容量、长度一起传递给函数，切片的[指针](https://www.geeksforgeeks.org/pointers-in-golang/)始终指向底层数组。因此，如果我们对通过值传递给函数的切片进行一些更改，这些更改将反映在函数外部的切片中。让我们借助一个例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how to
// pass a slice to the function
package main

import "fmt"

// Function in which slice
// is passed by value
func myfun(element []string) {

    // Modifying the given slice
    element[2] = "Java"
    fmt.Println("Modified slice: ", element)
}

// Main function
func main() {

    // Creating slice
    slc := []string{"C#", "Python", "C", "Perl"}

    fmt.Println("Initial slice: ", slc)

    // Passing the slice to the function
    myfun(slc)

    fmt.Println("Final slice:", slc)

}
```

**输出:**

```go
Initial slice:  [C# Python C Perl]
Modified slice:  [C# Python Java Perl]
Final slice: [C# Python Java Perl]

```

**说明:**在上例中，我们有一个名为 *slc* 的切片。该切片在 *myfun()* 函数中传递。我们知道*切片指针总是指向同一个引用*，即使它们是在函数中传递的。因此，当我们将值 C 更改为 Java 时，索引值为 2。这个变化也反映了函数外部存在的切片，所以修改后的最终切片是*【c# Python Java perl】*。

**例 2:**

```go
// Go program to illustrate how to
// pass a slice to the function
package main

import "fmt"

// Function in which slice
// is passed by value
func myfun(element []string) {

    // Here we only modify the slice
    // Using append function
    // Here, this function only modifies
    // the copy of the slice present in 
    // the function not the original slice
    element = append(element, "Java")
    fmt.Println("Modified slice: ", element)
}

// Main function
func main() {

    // Creating a slice
    slc := []string{"C#", "Python", "C", "Perl"}

    fmt.Println("Initial slice: ", slc)

    // Passing the slice
    // to the function

    myfun(slc)
    fmt.Println("Final slice: ", slc)

}
```

**输出:**

```go
Initial slice:  [C# Python C Perl]
Modified slice:  [C# Python C Perl Java]
Final slice:  [C# Python C Perl]

```