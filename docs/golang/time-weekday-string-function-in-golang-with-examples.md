# Golang 中的 time.Weekday.String()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-weekday-string-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-weekday-string-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 围棋语言中的**Weekday.String()**函数用于查找当天的英文名称。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (d Weekday) String() string

```

这里，“d”是工作日的类型。

**返回值：**它返回一个字符串，该字符串是当天的英文名称。

**示例：**

```go
// Golang program to illustrate the usage of
// Weekday.String() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling time.Weekday
    // with its parameter
    // of type int
    var d = time.Weekday(0)
    var e = time.Weekday(1)
    var f = time.Weekday(2)
    var g = time.Weekday(3)
    var h = time.Weekday(4)
    var i = time.Weekday(5)
    var j = time.Weekday(6)

    // Prints the English 
    // name of the day
    fmt.Println(d.String())
    fmt.Println(e.String())
    fmt.Println(f.String())
    fmt.Println(g.String())
    fmt.Println(h.String())
    fmt.Println(i.String())
    fmt.Println(j.String())
}
```

发帖主题：Re：Колибри0.7.8.0