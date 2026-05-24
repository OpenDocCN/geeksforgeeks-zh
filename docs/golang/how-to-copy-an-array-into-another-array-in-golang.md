# 如何在 Golang 中将一个数组复制成另一个数组？

> 原文:[https://www . geesforgeks . org/如何将一个阵列复制到另一个阵列中 golang/](https://www.geeksforgeeks.org/how-to-copy-an-array-into-another-array-in-golang/)

[Golang 或 Go 编程语言中的数组](https://www.geeksforgeeks.org/arrays-in-go/)与其他编程语言非常相似。在程序中，有时我们需要存储一组相同类型的数据，比如学生成绩列表。这种类型的集合存储在使用数组的程序中。数组是固定长度的序列，用于在内存中存储同类元素。Golang 没有提供特定的内置函数来将一个数组复制到另一个数组中。但是，我们可以通过简单地通过值或引用将数组赋给新变量来创建数组的副本。
如果我们通过值创建一个数组的副本，并对原始数组的值进行了一些更改，那么它将不会反映在该数组的副本中。如果我们通过引用创建了一个数组的副本，并对原始数组的值进行了一些更改，那么它将反映在该数组的副本中。如下例所示:

**语法:**

```go
// creating a copy of an array by value
arr := arr1

// Creating a copy of an array by reference
arr := &arr1

```

让我们借助例子来讨论这个概念:

**例 1:**

```go
// Go program to illustrate how
// to copy an array by value
package main

import "fmt"

func main() {

    // Creating and initializing an array
    // Using shorthand declaration
    my_arr1 := [5]string{"Scala", "Perl", "Java", "Python", "Go"}

    // Copying the array into new variable
    // Here, the elements are passed by value
    my_arr2 := my_arr1

    fmt.Println("Array_1: ", my_arr1)
    fmt.Println("Array_2:", my_arr2)

    my_arr1[0] = "C++"

    // Here, when we copy an array
    // into another array by value
    // then the changes made in original
    // array do not reflect in the
    // copy of that array
    fmt.Println("\nArray_1: ", my_arr1)
    fmt.Println("Array_2: ", my_arr2)
}
```

**输出:**

```go
Array_1:  [Scala Perl Java Python Go]
Array_2: [Scala Perl Java Python Go]

Array_1:  [C++ Perl Java Python Go]
Array_2:  [Scala Perl Java Python Go]

```

**例 2:**

```go
// Go program to illustrate how to
// copy an array by reference
package main

import "fmt"

func main() {

    // Creating and initializing an array
    // Using shorthand declaration
    my_arr1 := [6]int{12, 456, 67, 65, 34, 34}

    // Copying the array into new variable
    // Here, the elements are passed by reference
    my_arr2 := &my_arr1

    fmt.Println("Array_1: ", my_arr1)
    fmt.Println("Array_2:", *my_arr2)

    my_arr1[5] = 1000000

    // Here, when we copy an array 
    // into another array by reference
    // then the changes made in original 
    // array will reflect in the
    // copy of that array
    fmt.Println("\nArray_1: ", my_arr1)
    fmt.Println("Array_2:", *my_arr2)
}
```

**输出:**

```go
Array_1:  [12 456 67 65 34 34]
Array_2: [12 456 67 65 34 34]

Array_1:  [12 456 67 65 34 1000000]
Array_2: [12 456 67 65 34 1000000]

```