# 如何在 Golang 中使用 for 循环迭代数组？

> 原文:[https://www . geesforgeks . org/如何在数组上迭代使用 for 循环 golang/](https://www.geeksforgeeks.org/how-to-iterate-over-an-array-using-for-loop-in-golang/)

[数组](https://www.geeksforgeeks.org/arrays-in-go/)是存储在连续位置的相似类型项目集合的数据结构。为了在数组上执行操作，需要遍历它。循环的**用于在编程语言中迭代数据结构。这里可以通过以下方式使用它:**

**例 1:**

```go
// Golang program to iterate over
// an Array using for loop
package main

import "fmt"

func main() {

    // taking an array
    arr := [5]int{1, 2, 3, 4, 5}
    fmt.Println("The elements of the array are: ")

    // using for loop
    for i := 0; i < len(arr); i++ {
        fmt.Println(arr[i])
    }
}
```

**输出:**

```go
The elements of the array are:
1
2
3
4
5

```

**解释:**变量 I 被初始化为 0，并被定义为每次迭代都增加，直到它达到数组长度的值。然后给出打印命令，逐个打印数组每个索引处的元素。

**示例 2:**for 循环可以使用另一个关键字**返回**来执行迭代。

```go
// Golang program to iterate over
// an Array using for loop
package main

import "fmt"

func main() {

    // taking an array
    arr := [5]string{"Ronaldo", "Messi", "Kaka", "James", "Casillas"}
    fmt.Println("The elements of the array are:")

    // using for loop
    for index, element := range arr {
        fmt.Println("At index", index, "value is", element)
    }
}
```

**输出:**

```go
The elements of the array are:
At index 0 value is Ronaldo
At index 1 value is Messi
At index 2 value is Kaka
At index 3 value is James
At index 4 value is Casillas

```

**说明:**关键字**范围**设置迭代范围至 arr 长度。变量索引和元素分别存储数组的索引和值。

**例 3:** 当我们不需要索引时，可以用空白标识符 _，忽略它。

```go
// Golang program to iterate over
// an Array using for loop
package main

import "fmt"

func main() {

    // taking an array
    arr := []int{1, 2, 3, 4, 5}
    fmt.Println("The elements of the array are:")

    // using for loop
    for _, value := range arr {
        fmt.Println(value)
    }
}
```

**输出:**

```go
The elements of the array are:
1
2
3
4
5

```