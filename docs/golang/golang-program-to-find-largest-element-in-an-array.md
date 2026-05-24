# 寻找数组中最大元素的 Golang 程序

> 原文:[https://www . geesforgeks . org/golang-program-to-find-最大数组元素/](https://www.geeksforgeeks.org/golang-program-to-find-largest-element-in-an-array/)

任务是通过从用户那里获取输入值来找到 Golang 中[数组](https://www.geeksforgeeks.org/arrays-in-go/)的最大元素。

**示例:**

> 输入:输入元素数量:4
> 
> 输入数字:40
> 输入数字:69
> 输入数字:89
> 输入数字:-54
> 
> 输出:最大数量为:89

在这个程序中，用户需要输入他想要执行比较的元素总数和值。程序将比较所有元素，并返回最大元素的值。

```go
// Golang Program to Find Largest Element in an Array
package main

import "fmt"

func main() {

// taking an array variable
    var n [100]float64
    var total int
    fmt.Print("Enter number of elements: ")

    // taking user input
    fmt.Scanln(&total)
    for i := 0; i < total; i++ {
        fmt.Print("Enter the number : ")
        fmt.Scan(&n[i])
    }
    for j := 1; j < total; j++ {
        if n[0] < n[j] {
            n[0] = n[j]
        }

    }

    fmt.Print("The largest number is : ", n[0])
}
```

**输出:**

> 输入元素数量:5
> 输入数量:20
> 输入数量:-219
> 输入数量:219
> 输入数量:54.87
> 输入数量:-1000
> 最大数量为:219

**说明:**在上面的程序中，我们首先从用户处获取输入值。我们取一个存储数组大小的变量 temp。然后，进行比较，直到我们到达最后一个元素。然后循环终止，最大元素的值返回给用户。