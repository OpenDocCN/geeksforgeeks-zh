# Golang 中的范围关键字

> 原文:[https://www.geeksforgeeks.org/range-keyword-in-golang/](https://www.geeksforgeeks.org/range-keyword-in-golang/)

在 Golang **范围内**关键字用于不同类型的数据结构，以便迭代元素。**范围**关键字主要用于 for 循环，以便迭代一个 [**地图**](https://www.geeksforgeeks.org/golang-maps/)[**切片**](https://www.geeksforgeeks.org/slices-in-golang/)[**通道**](https://www.geeksforgeeks.org/channel-in-golang/) 或一个 [**数组**](https://www.geeksforgeeks.org/arrays-in-go/) 的所有元素。当它遍历数组的元素并进行切片时，它以整数形式返回元素的索引。当它遍历一个映射的元素时，它返回下一个键值对的键。此外，*范围*可以返回一个值或两个值。*让我们看看在 Golang 中迭代不同种类的集合时*范围*返回什么。*

*   **Array or slice:** In the case of array or slice, the first value returned is *index* , and the second value is *element* .
*   **String:** The first value returned in the string is *index* , and the second value is *rune int* .
*   **Map:** The first value returned in the map is the *key* , and the second value is the *value* of the key-value pair in the map.
*   **Channel:** The first value returned in the channel is *element* , and the second value is *none* .

现在我们来看一些例子来说明 **range 关键字**在 Golang 中的用法。

**例 1:**

```go
// Golang Program to illustrate the usage
// of range keyword over items of an
// array in Golang

package main

import "fmt"

// main function
func main() {

    // Array of odd numbers
    odd := [7]int{1, 3, 5, 7, 9, 11, 13}

    // using range keyword with for loop to
    // iterate over the array elements
    for i, item := range odd {

        // Prints index and the elements
        fmt.Printf("odd[%d] = %d \n", i, item)
    }
}
```

**输出:**

```go
odd[0] = 1
odd[1] = 3
odd[2] = 5
odd[3] = 7
odd[4] = 9
odd[5] = 11
odd[6] = 13

```

这里，所有元素都打印有各自的索引。

**例 2:**

```go
// Golang Program to illustrate the usage of
// range keyword over string in Golang

package main

import "fmt"

// Constructing main function
func main() {

    // taking a string
    var string = "GeeksforGeeks"

    // using range keyword with for loop to
    // iterate over the string
    for i, item := range string {

        // Prints index of all the
        // characters in the string
        fmt.Printf("string[%d] = %d \n", i, item)
    }
}
```

**输出:**

```go
string[0] = 71 
string[1] = 101 
string[2] = 101 
string[3] = 107 
string[4] = 115 
string[5] = 102 
string[6] = 111 
string[7] = 114 
string[8] = 71 
string[9] = 101 
string[10] = 101 
string[11] = 107 
string[12] = 115

```

这里打印的项目是*符文*，即构成字符串的所述字符的 *int32* ASCII 值。

**例 3:**

```go
// Golang Program to illustrate the usage of
// range keyword over maps in Golang

package main

import "fmt"

// main function
func main() {

    // Creating map of student ranks
    student_rank_map := map[string]int{"Nidhi": 3,
                           "Nisha": 2, "Rohit": 1}

    // Printing map using keys only
    for student := range student_rank_map {
        fmt.Println("Rank of", student, "is: ",
                     student_rank_map[student])
    }

    // Printing maps using key-value pair
    for student, rank := range student_rank_map {
        fmt.Println("Rank of", student, "is: ", rank)
    }
}
```

**输出:**

```go
Rank of Nidhi is:  3
Rank of Nisha is:  2
Rank of Rohit is:  1
Rank of Nidhi is:  3
Rank of Nisha is:  2
Rank of Rohit is:  1

```

因此，这里首先只使用键打印输出，然后再次使用键和值打印输出。