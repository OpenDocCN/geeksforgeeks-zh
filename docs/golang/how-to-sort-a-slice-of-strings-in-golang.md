# 如何对 Golang 中的一段字符串进行排序？

> 原文:[https://www . geesforgeks . org/如何对 golang 中的字符串片段进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-slice-of-strings-in-golang/)

In Go 语言切片比[数组](https://www.geeksforgeeks.org/arrays-in-go/)更强大、灵活、方便，是一种轻量级的数据结构。[切片](https://www.geeksforgeeks.org/slices-in-golang/)是存储相似类型元素的可变长度序列，不允许在同一个切片中存储不同类型的元素。Go 语言允许您根据切片的类型对其元素进行排序。因此，使用以下函数对字符串类型切片进行排序。这些函数是在排序包下定义的，因此您必须在程序中导入排序包来访问这些函数:

**1。Strings:** 这个函数只用于对字符串的一个切片进行排序，它按照递增的顺序对切片的元素进行排序。

**语法:**

```go
func Strings(scl []string)
```

这里， *slc* 代表一段字符串。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how
// to sort the slice of strings
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing slices
    // Using shorthand declaration
    scl1 := []string{"abc", "rwp", "def", "por", "ber", "erj"}
    scl2 := []string{"Rabbit", "Fish", "Dog",
              "Parrot", "Cat", "Hamster"}

    // Displaying slices
    fmt.Println("Slices(Before):")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)

    // Sorting the slice of strings
    // Using Strings function
    sort.Strings(scl1)
    sort.Strings(scl2)

    // Displaying the result
    fmt.Println("\nSlices(After):")
    fmt.Println("Slice 1 : ", scl1)
    fmt.Println("Slice 2 : ", scl2)
}
```

**输出:**

```go
Slices(Before):
Slice 1:  [abc rwp def por ber erj]
Slice 2:  [Rabbit Fish Dog Parrot Cat Hamster]

Slices(After):
Slice 1 :  [abc ber def erj por rwp]
Slice 2 :  [Cat Dog Fish Hamster Parrot Rabbit]

```

**2。字符串排序:**该函数用于检查给定的字符串片段是否是排序形式(按递增顺序)。如果切片处于排序形式，此方法返回 true 如果切片不处于排序形式，则返回 false。

**语法:**

```go
func StringsAreSorted(scl []string) bool
```

这里， *scl* 代表一段字符串。让我们借助一个例子来讨论这个概念:

**示例:**

```go
// Go program to illustrate how to check
// whether the given slice of strings
// is in sorted form or not
package main

import (
    "fmt"
    "sort"
)

// Main function
func main() {

    // Creating and initializing slices
    // Using shorthand declaration
    scl1 := []string{"abc", "ber", "def", "erj", "por", "rwp"}
    scl2 := []string{"Rabbit", "Fish", "Dog",
                  "Parrot", "Cat", "Hamster"}

    // Displaying slices
    fmt.Println("Slices:")
    fmt.Println("Slice 1: ", scl1)
    fmt.Println("Slice 2: ", scl2)

    // Checking the slice is in sorted form or not
    // Using StringsAreSorted function
    res1 := sort.StringsAreSorted(scl1)
    res2 := sort.StringsAreSorted(scl2)

    // Displaying the result
    fmt.Println("\nResult:")
    fmt.Println("Is Slice 1 is sorted?: ", res1)
    fmt.Println("Is Slice 2 is sorted?: ", res2)
}
```

**输出:**

```go
Slices:
Slice 1:  [abc ber def erj por rwp]
Slice 2:  [Rabbit Fish Dog Parrot Cat Hamster]

Result:
Is Slice 1 is sorted?:  true
Is Slice 2 is sorted?:  false

```