# 如何使用 Golang 中的数组计算平均值？

> 原文：[https://www.geeksforgeeks.org/how-to-calculate-the-average-using-arrays-in-golang/](https://www.geeksforgeeks.org/how-to-calculate-the-average-using-arrays-in-golang/)

给定一个由 `n` 个元素组成的[数组](https://www.geeksforgeeks.org/arrays-in-go/)，你的任务是找出数组的平均值。

**步骤：**

*   接受数组的大小。
*   接受数组的元素。
*   使用 `for` 循环存储元素的和。
*   计算平均值 = (`sum` / 数组大小`)。
*   打印平均值。

**示例：**

```go
Input:
n = 4
array = 1, 2, 3, 4

Output:
sum = 10
average = 2.5
```

## 代码实现

```go
// Golang program to Calculate the Average using Arrays
package main

import "fmt"

func main() {

    // declaring an array of values
    array := []int{1, 2, 3, 4}

    // size of the array
    n := 4

    // declaring a variable
    // to store the sum
    sum := 0

    // traversing through the
    // array using for loop
    for i := 0; i < n; i++ {

        // adding the values of
        // array to the variable sum
        sum += (array[i])
    }

    // declaring a variable
    // avg to find the average
    avg := (float64(sum)) / (float64(n))

    // typecast all values to float
    // to get the correct result
    fmt.Println("Sum = ", sum, "\nAverage = ", avg)
}
```

**输出**

```go
Sum =  10
Average =  2.5
```

这里，`n` 是数组的大小，`sum` 是存储数组所有值的和。使用 `for` 循环，我们找到数组元素的和。计算总和后，我们必须将 `sum` 的数据类型和数组的大小转换为 `float64`，这样我们就不会丢失任何十进制值。

要了解更多方法，您可以浏览文章[数组平均值的编程(迭代和递归)](https://www.geeksforgeeks.org/program-average-array-iterative-recursive/)。