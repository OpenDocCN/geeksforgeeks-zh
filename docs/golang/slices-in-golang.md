# 格朗切片

> 原文:[https://www.geeksforgeeks.org/slices-in-golang/](https://www.geeksforgeeks.org/slices-in-golang/)

In Go 语言切片比[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一种轻量级的数据结构。切片是存储相似类型元素的可变长度序列，不允许在同一切片中存储不同类型的元素。它就像一个有索引值和长度的数组，但是切片的大小被调整，它们不像数组那样是固定大小的。在内部，切片和数组是相互连接的，切片是对底层数组的引用。允许在切片中存储重复的元素。 ***切片中的第一个索引位置始终为 0，最后一个索引位置将为(切片长度–1)***。

### 切片声明

切片就像数组一样被声明，但是它不包含切片的大小。所以它可以根据需要生长或收缩。

**语法:**

```go
[]T
or 
[]T{}
or 
[]T{value1, value2, value3, ...value n}
```

这里，T 是元素的类型。例如:

```go
var my_slice[]int 
```

### 切片的组件

切片包含三个组件:

*   [**指针**](https://www.geeksforgeeks.org/pointers-in-golang/) **:** 指针用于指向可通过切片访问的数组的第一个元素。这里，指向的元素不必是数组的第一个元素。
*   **长度:**长度是数组中存在的元素总数。
*   **容量:**容量代表它可以扩展到的最大大小。

让我们借助一个例子来讨论所有这些组件:

**示例:**

## 去

```go
// Golang program to illustrate
// the working of the slice components
package main

import "fmt"

func main() {

    // Creating an array
    arr := [7]string{"This", "is", "the", "tutorial",
                         "of", "Go", "language"}

    // Display array
    fmt.Println("Array:", arr)

    // Creating a slice
    myslice := arr[1:6]

    // Display slice
    fmt.Println("Slice:", myslice)

    // Display length of the slice
    fmt.Printf("Length of the slice: %d", len(myslice))

    // Display the capacity of the slice
    fmt.Printf("\nCapacity of the slice: %d", cap(myslice))
}
```

**输出:**

```go
Array: [This is the tutorial of Go language]
Slice: [is the tutorial of Go]
Length of the slice: 5
Capacity of the slice: 6
```

**解释:**在上面的例子中，我们从给定的数组中创建一个切片。这里，切片的指针指向索引 1，因为切片的下限设置为 1，所以它开始从索引 1 访问元素。切片的长度是 5，这意味着切片中存在的元素总数是 5，切片 6 的容量意味着它最多可以在其中存储 6 个元素。

![](img/e055a65b627965661fac30008b53be8d.png)

### 如何创建和初始化切片？

在 Go 语言中，可以使用以下方式创建和初始化切片:

*   **使用切片文字:**您可以使用切片文字创建切片。切片文字的创建就像一个数组文字，但是有一点不同，就是不允许在方括号[]中指定切片的大小。如下例所示，该表达式的右侧是切片文字。

```go
var my_slice_1 = []string{"Geeks", "for", "Geeks"}
```

**注意:**永远记住，当你使用字符串创建一个切片时，它首先创建一个数组，然后返回一个切片引用给它。

**示例:**

## 去

```go
// Golang program to illustrate how
// to create a slice using a slice
// literal
package main

import "fmt"

func main() {

    // Creating a slice
    // using the var keyword
    var my_slice_1 = []string{"Geeks", "for", "Geeks"}

    fmt.Println("My Slice 1:", my_slice_1)

    // Creating a slice
    //using shorthand declaration
    my_slice_2 := []int{12, 45, 67, 56, 43, 34, 45}
    fmt.Println("My Slice 2:", my_slice_2)
}
```

**输出:**

```go
My Slice 1: [Geeks for Geeks]
My Slice 2: [12 45 67 56 43 34 45]
```

*   **使用数组:**我们已经知道 ***切片是数组*** 的参考，因此您可以从给定的数组创建切片。要从给定的数组创建切片，首先需要指定下限和上限，这意味着切片可以从数组中的元素开始，从下限到上限。它不包括上限以上的元素。如下例所示:
    **语法:**

```go
array_name[low:high]
```

该语法将返回一个新的切片。

**注意:**下界的默认值为 0，上界的默认值为给定数组中存在的元素总数。

**示例:**

## 去

```go
// Golang program to illustrate how to
// create slices from the array
package main

import "fmt"

func main() {

    // Creating an array
    arr := [4]string{"Geeks", "for", "Geeks", "GFG"}

    // Creating slices from the given array
    var my_slice_1 = arr[1:2]
    my_slice_2 := arr[0:]
    my_slice_3 := arr[:2]
    my_slice_4 := arr[:]

    // Display the result
    fmt.Println("My Array: ", arr)
    fmt.Println("My Slice 1: ", my_slice_1)
    fmt.Println("My Slice 2: ", my_slice_2)
    fmt.Println("My Slice 3: ", my_slice_3)
    fmt.Println("My Slice 4: ", my_slice_4)
}
```

**输出:**

```go
My Array:  [Geeks for Geeks GFG]
My Slice 1:  [for]
My Slice 2:  [Geeks for Geeks GFG]
My Slice 3:  [Geeks for]
My Slice 4:  [Geeks for Geeks GFG]
```

*   **使用已经存在的切片:**也允许从给定的切片创建切片。要从给定切片创建切片，首先需要指定下限和上限，这意味着切片可以从给定切片的元素开始，从下限到上限。它不包括上限以上的元素。如下例所示:
    **语法:**

```go
slice_name[low:high]
```

该语法将返回一个新的切片。

**注意:**下界的默认值为 0，上界的默认值为给定切片中存在的元素总数。

**示例:**

## 去

```go
// Golang program to illustrate how to
// create slices from the slice
package main

import "fmt"

func main() {

    // Creating s slice
    oRignAl_slice := []int{90, 60, 40, 50,
        34, 49, 30}

    // Creating slices from the given slice
    var my_slice_1 = oRignAl_slice[1:5]
    my_slice_2 := oRignAl_slice[0:]
    my_slice_3 := oRignAl_slice[:6]
    my_slice_4 := oRignAl_slice[:]
    my_slice_5 := my_slice_3[2:4]

    // Display the result
    fmt.Println("Original Slice:", oRignAl_slice)
    fmt.Println("New Slice 1:", my_slice_1)
    fmt.Println("New Slice 2:", my_slice_2)
    fmt.Println("New Slice 3:", my_slice_3)
    fmt.Println("New Slice 4:", my_slice_4)
    fmt.Println("New Slice 5:", my_slice_5)
}
```

**输出:**

```go
Original Slice: [90 60 40 50 34 49 30]
New Slice 1: [60 40 50 34]
New Slice 2: [90 60 40 50 34 49 30]
New Slice 3: [90 60 40 50 34 49]
New Slice 4: [90 60 40 50 34 49 30]
New Slice 5: [40 50]
```

*   **使用 make()函数:**还可以使用 go library 提供的 *make()函数*创建切片。该函数采用三个参数，即类型、长度和容量。这里，容量值是可选的。它分配一个大小等于给定容量的底层数组，并返回一个指向底层数组的切片。通常，make()函数用于创建一个空切片。这里，空切片是那些包含空数组引用的切片。
    **语法:**

```go
func make([]T, len, cap) []T
```

**示例:**

## 去

```go
// Go program to illustrate how to create slices
// Using make function
package main

import "fmt"

func main() {

    // Creating an array of size 7
    // and slice this array  till 4
    // and return the reference of the slice
    // Using make function
    var my_slice_1 = make([]int, 4, 7)
    fmt.Printf("Slice 1 = %v, \nlength = %d, \ncapacity = %d\n",
                   my_slice_1, len(my_slice_1), cap(my_slice_1))

    // Creating another array of size 7
    // and return the reference of the slice
    // Using make function
    var my_slice_2 = make([]int, 7)
    fmt.Printf("Slice 2 = %v, \nlength = %d, \ncapacity = %d\n",
                   my_slice_2, len(my_slice_2), cap(my_slice_2))

}
```

**输出:**

```go
Slice 1 = [0 0 0 0], 
length = 4, 
capacity = 7
Slice 2 = [0 0 0 0 0 0 0], 
length = 7, 
capacity = 7
```

### 如何迭代切片？

您可以使用以下方法迭代切片:

*   **使用 for 循环:**最简单的迭代切片方式如下例所示:
    **例:**

## 去

```go
// Golang program to illustrate the
// iterating over a slice using
// for loop
package main

import "fmt"

func main() {

    // Creating a slice
    myslice := []string{"This", "is", "the", "tutorial",
        "of", "Go", "language"}

    // Iterate using for loop
    for e := 0; e < len(myslice); e++ {
        fmt.Println(myslice[e])
    }
}
```

**输出:**

```go
This
is
the
tutorial
of
Go
language
```

*   **使用 for 循环中的范围:**允许使用 for 循环中的范围迭代切片。使用 for 循环中的 range，可以获得索引和元素值，如示例所示:
    **示例:**

## 去

```go
// Golang program to illustrate the iterating
// over a slice using range in for loop
package main

import "fmt"

func main() {

    // Creating a slice
    myslice := []string{"This", "is", "the", "tutorial",
                                 "of", "Go", "language"}

    // Iterate slice
    // using range in for loop
    for index, ele := range myslice {
        fmt.Printf("Index = %d and element = %s\n", index+3, ele)
    }
}
```

**输出:**

```go
Index = 3 and element = This
Index = 4 and element = is
Index = 5 and element = the
Index = 6 and element = tutorial
Index = 7 and element = of
Index = 8 and element = Go
Index = 9 and element = language
```

*   **在 for 循环中使用空白标识符:**在 for 循环的范围内，如果不想获取元素的索引值，可以使用空格(_)代替索引变量，如下例所示:
    **例:**

## 去

```go
// Golang program to illustrate the iterating over
// a slice using range in for loop without an index
package main

import "fmt"

func main() {

    // Creating a slice
    myslice := []string{"This", "is", "the",
        "tutorial", "of", "Go", "language"}

    // Iterate slice
    // using range in for loop
    // without index
    for _, ele := range myslice {
        fmt.Printf("Element = %s\n", ele)
    }
}
```

**输出:**

```go
Element = This
Element = is
Element = the
Element = tutorial
Element = of
Element = Go
Element = language
```

### 关于切片的要点

*   **零值切片:**在 Go 语言中，允许创建一个不包含任何元素的零值切片。所以这个切片的容量和长度是 0。无切片不包含数组引用，如下例所示:
    **例:**

## 去

```go
// Go program to illustrate a zero value slice
package main

import "fmt"

func main() {

    // Creating a zero value slice
    var myslice []string
    fmt.Printf("Length = %d\n", len(myslice))
    fmt.Printf("Capacity = %d ", cap(myslice))

}
```

**输出:**

```go
Length = 0
Capacity = 0
```

*   **修改切片:**因为我们已经知道切片是引用类型，所以它可以引用底层数组。因此，如果我们更改切片中的一些元素，那么更改也应该发生在引用的数组中。或者换句话说，如果您对切片进行了任何更改，那么它也会反映在数组中，如下例所示:
    **例:**

## 去

```go
// Golang program to illustrate
// how to modify the slice
package main

import "fmt"

func main() {

    // Creating a zero value slice
    arr := [6]int{55, 66, 77, 88, 99, 22}
    slc := arr[0:4]

    // Before modifying

    fmt.Println("Original_Array: ", arr)
    fmt.Println("Original_Slice: ", slc)

    // After modification
    slc[0] = 100
    slc[1] = 1000
    slc[2] = 1000

    fmt.Println("\nNew_Array: ", arr)
    fmt.Println("New_Slice: ", slc)
}
```

**输出:**

```go
Original_Array:  [55 66 77 88 99 22]
Original_Slice:  [55 66 77 88]

New_Array:  [100 1000 1000 88 99 22]
New_Slice:  [100 1000 1000 88]
```

*   **切片的比较:**在切片中，只能使用 **==** 操作符检查给定切片是否为 nill。如果你试图在 **==** 操作符的帮助下比较两个切片，那么它会给你一个错误，如下例所示:
    **例:**

## 去

```go
// Golang program to check if
// the slice is nil or not
package main

import "fmt"

func main() {

    // creating slices
    s1 := []int{12, 34, 56}
    var s2 []int

    // If you try to run this commented
    // code compiler will give an error
    /*s3:= []int{23, 45, 66}
      fmt.Println(s1==s3)
    */

    // Checking if the given slice is nil or not
    fmt.Println(s1 == nil)
    fmt.Println(s2 == nil)
}
```

**输出:**

```go
false
true
```

**注意:**如果要比较两个切片，那么使用 range for loop 来匹配每个元素，或者可以使用 *DeepEqual* 功能。

*   **多维切片:**多维切片就像多维数组一样，只是切片不包含大小。
    T3】例:

## 去

```go
// Go program to illustrate the multi-dimensional slice
package main

import "fmt"

func main() {

    // Creating multi-dimensional slice
    s1 := [][]int{{12, 34},
        {56, 47},
        {29, 40},
        {46, 78},
    }

    // Accessing multi-dimensional slice
    fmt.Println("Slice 1 : ", s1)

    // Creating multi-dimensional slice
    s2 := [][]string{
        []string{"Geeks", "for"},
        []string{"Geeks", "GFG"},
        []string{"gfg", "geek"},
    }

    // Accessing multi-dimensional slice
    fmt.Println("Slice 2 : ", s2)

}
```

**输出:**

```go
Slice 1 :  [[12 34] [56 47] [29 40] [46 78]]
Slice 2 :  [[Geeks for] [Geeks GFG] [gfg geek]]
```

*   **切片的排序:**在 Go 语言中，允许对切片中存在的元素进行排序。Go 语言的标准库提供了包含不同类型排序方法的排序包，用于对 *ints* 、 *float64s* 和*string*的切片进行排序。这些函数总是按升序对可用的元素进行排序。
    **示例:**

## 去

```go
// Go program to illustrate how to sort
// the elements present in the slice
package main

import (
    "fmt"
    "sort"
)

func main() {

    // Creating Slice
    slc1 := []string{"Python", "Java", "C#", "Go", "Ruby"}
    slc2 := []int{45, 67, 23, 90, 33, 21, 56, 78, 89}

    fmt.Println("Before sorting:")
    fmt.Println("Slice 1: ", slc1)
    fmt.Println("Slice 2: ", slc2)

    // Performing sort operation on the
    // slice using sort function
    sort.Strings(slc1)
    sort.Ints(slc2)

    fmt.Println("\nAfter sorting:")
    fmt.Println("Slice 1: ", slc1)
    fmt.Println("Slice 2: ", slc2)

}
```

**输出:**

```go
Before sorting:
Slice 1:  [Python Java C# Go Ruby]
Slice 2:  [45 67 23 90 33 21 56 78 89]

After sorting:
Slice 1:  [C# Go Java Python Ruby]
Slice 2:  [21 23 33 45 56 67 78 89 90]
```