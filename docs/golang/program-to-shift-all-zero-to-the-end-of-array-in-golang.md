# 在 Golang 中编程将所有的零移动到数组的末尾

> 原文:[https://www . geeksforgeeks . org/program-to-shift-all-zero-to-end-of-array-in-golang/](https://www.geeksforgeeks.org/program-to-shift-all-zero-to-the-end-of-array-in-golang/)

任务是将数组中出现的所有零移动到数组的末尾。在 Golang，这可以通过以下方式实现:

**例:**

```go
Input: 1 0 7 0 3

Output: 1 7 3 0 0

```

```go
// Golang program to shift all zero to the end of an array
package main

import (
    "fmt"
)

func main() {

    var c int

    // Creating an array of tiny type
    // Using var keyword
    var ar [5]int

    // Elements are assigned using index
    ar[0] = 1
    ar[1] = 0
    ar[2] = 7
    ar[3] = 0
    ar[4] = 3

    // taking the length of array
    var arr_ele_number = len(ar)
    c = 0

    for i := 0; i < arr_ele_number; i++ {

        if ar[i] != 0 {

            ar = ar[i]

            c = c + 1

        }
    }

    // Filling the remaining array
    // count index to zero
    for c != arr_ele_number {

        ar = 0

        c = c + 1

    }

    fmt.Println("The array elements after shifting all zero to ends:")

    for i := 0; i < arr_ele_number; i++ {

        fmt.Printf("%d ", ar[i])

    }
}
```

**输出:**

```go
The array elements after shifting all zero to ends:
1 7 3 0 0 

```

**说明:**上面例子背后的逻辑是用户输入元素的个数以及这些元素的值。然后，在搜索零的同时遍历数组，然后将零移动到数组的末尾。