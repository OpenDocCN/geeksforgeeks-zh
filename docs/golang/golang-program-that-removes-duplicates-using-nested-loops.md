# 使用嵌套循环删除重复项的 Golang 程序

> 原文:[https://www . geeksforgeeks . org/golang-移除重复项的程序-使用嵌套循环/](https://www.geeksforgeeks.org/golang-program-that-removes-duplicates-using-nested-loops/)

给定一个大小为 n 的数组。您的任务是从数组中移除重复的。

**示例:**

```go
Input : array: 1 2 1 2 1 3 2 
Output :1 2 3

Input :array: 10 24 5 10 24
Output :10 24 5

```

我们将使用两个循环来解决这个问题。第一个循环 **i** 将从 0 遍历到数组的长度。第二个循环将从 0 遍历到 **i-1** 。该循环用于确保索引 **i** 处的元素没有出现在 **i** 之前。如果那个元素以前来过，那么我们从第二个循环出来。就在第二个循环之后，我们写一个 if 条件，检查 *j = = i* 。如果它们相等，则意味着索引 **i** 处的元素以前没有出现过。所以我们必须将元素附加到结果数组中。

```go
// Golang Program that Removes
// Duplicates Using Nested Loops
package main

import "fmt"

func removeDup(a []int, n int) []int {

    // declaring an empty array
    result := []int{}

    // traversing the array
    // from 0 to length of array
    for i := 0; i < n; i++ {

        j := 0 // variable for next loop

        // loop to check if the current
        // element has come before or not
        for ; j < i; j++ {

            if a[j] == a[i] {
                // it means the element
                // has come before, so break
                break
            }
        }

        // it means that the element has not
        // come anytime, so append it in
        // the resultant array
        if j == i {
            result = append(result, a[i])
        }

    }
    return result

}

func main() {

    // declaring the array
    a := []int{1, 2, 1, 2, 1, 3, 2}

    // size of the array
    n := 7

    // calling the remove duplicates
    // function to get the answer
    result := removeDup(a, n)

    // printing the answer
    fmt.Println(result)

}
```

**输出:**

```go
[1 2 3]

```