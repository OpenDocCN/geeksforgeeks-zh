# 如何在 Golang 中将零终止字节数组转换为字符串？

> 原文:[https://www . geesforgeks . org/如何将以零结尾的字节数组转换为 golang 中的字符串/](https://www.geeksforgeeks.org/how-to-convert-a-zero-terminated-byte-array-to-string-in-golang/)

这里的任务是在 Golang 中将一个以零结尾的字节数组转换为字符串，可以使用以下方法:

**1。string()函数:**用于将以零结尾的字节数组转换为字符串。

**语法:**

```go
str := string(byteArray[:])

```

**示例:**

```go
// Go program to illustrate how to 
// convert a zero terminated byte
// array to string.

package main

import (
        "fmt"
)

func main() {

    // zero terminated byte
    // array
     arr := [20]byte{'a', 'b', 'c' , '1', '2', '3'}

    // printing the array
     fmt.Println("Array: ", arr)

     // convert a zero terminated
     // byte array to string
     // using string() method
     str := string(arr[:])

     // printing the converting
     // string
     fmt.Println("Conversion to string: ", str)  
}
```

**输出:**

```go
Array:  [97 98 99 49 50 51 0 0 0 0 0 0 0 0 0 0 0 0 0 0]
Conversion to string:  abc123

```

**2。Sprintf()函数:**它也用于将以零结尾的字节数组转换为字符串。但是性能不如前面的功能。

**语法:**

```go
str := fmt.Sprintf("%s", byteArray)

```

**示例:**

```go
// Go program to illustrate how to 
// convert a zero terminated byte
// array to string.

package main

import (
        "fmt"
)

func main() {

    // zero terminated byte
    // array
     arr := [20]byte{'a', 'b', 'c' , '1', '2', '3'}

    // printing the array
     fmt.Println("Array: ", arr)

     // convert a zero terminated
     // byte array to string
     // using Sprintf() method
     str := fmt.Sprintf("%s", arr)

     // printing the converting
     // string
     fmt.Println("Conversion to string: ", str)

}
```

**输出:**

```go
Array:  [97 98 99 49 50 51 0 0 0 0 0 0 0 0 0 0 0 0 0 0]
Conversion to string:  abc123

```