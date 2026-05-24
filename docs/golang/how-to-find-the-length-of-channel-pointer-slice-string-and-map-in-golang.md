# 如何在 Golang 中找到通道、指针、切片、字符串和地图的长度？

> 原文:[https://www . geeksforgeeks . org/如何在 golang 中查找通道长度指针切片字符串和映射/](https://www.geeksforgeeks.org/how-to-find-the-length-of-channel-pointer-slice-string-and-map-in-golang/)

在 Golang 中， **len** 函数用于查找一个[通道的长度](https://www.geeksforgeeks.org/channel-in-golang/)、[指针](https://www.geeksforgeeks.org/pointers-in-golang/)、[切片](https://www.geeksforgeeks.org/slices-in-golang/)、[字符串](https://www.geeksforgeeks.org/strings-in-golang/)、[映射](https://www.geeksforgeeks.org/golang-maps/)。

**通道:**在 Go 语言中，通道是一个 goro tine 与另一个 goro tine 通信的媒介，这种通信是无锁的。

```go
// Go program to illustrate
// how to find the length a channel
package main

import "fmt"

func main() {

    // Creating a channel using make() function
    ch:= make(chan int, 5)
    fmt.Printf("\nChannel: %d", len(ch))
    ch <- 0
    ch <- 1
    ch <- 2
    fmt.Printf("\nChannel: %d", len(ch))
}
```

**输出:**

```go
Channel: 0
Channel: 3

```

**指针:**Go 编程语言或 Golang 中的指针是一个变量，用于存储另一个变量的内存地址。

```go
// Go program to illustrate
// how to find the length a Pointer.
package main

import "fmt"

func main() {

    // Creating a pointer
    var poin *[10]string
    fmt.Printf("\nPointer: %d", len(poin))
}
```

**输出:**

```go
Pointer: 10

```

**切片:**切片是存储相似类型元素的变长序列，不允许在同一个切片中存储不同类型的元素。

```go
// Go program to illustrate
// how to find length Slice
package main

import "fmt"

func main() {

    // Creating a slice using make() function
    sliceEx := make([]int, 10)
    fmt.Printf("\nSlice: %d", len(sliceEx))
}
```

**输出:**

```go
Slice: 10

```

**字符串:**它是一个可变宽度字符序列，其中每个字符都由一个或多个字节使用 UTF-8 编码来表示。

```go
// Go program to illustrate
// how to find length a String.
package main

import "fmt"

func main() {
    // Creating a string
    strEx := "India"
    fmt.Printf("\nString: %d", len(strEx))
}
```

**输出:**

```go
String: 5

```

**地图:** Golang Maps 是一组无序的键值对的集合。

```go
// Go program to illustrate
// how to find length a Map.
package main

import "fmt"

func main() {

    // Creating a map using make() function
    mapEx := make(map[string]int)
    mapEx["A"] = 10
    mapEx["B"] = 20
    mapEx["C"] = 30
    fmt.Printf("\nMap: %d", len(mapEx))
}
```

**输出:**

```go
Map: 3

```