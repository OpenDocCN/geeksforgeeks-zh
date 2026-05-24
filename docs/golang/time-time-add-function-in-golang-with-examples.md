# Golang 中的 time.Time.Add()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-add-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-add-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 围棋语言中的**Time.Add()**函数用于添加指定的时间和持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Add(d Duration) Time

```

这里，“t”是规定的时间，“d”是要加到规定的时间上的持续时间。

**返回值：**返回所述 t 和 d 相加的结果。

**示例：**

```go
// Golang program to illustrate the usage of
// Time.Add() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring time in UTC
    t := time.Date(2020, 11, 9, 7, 0, 0, 0, time.UTC)

    // Declaring durations
    d1 := t.Add(time.Second * 4)
    d2 := t.Add(time.Minute * 2)
    d3 := t.Add(time.Hour * 1)
    d4 := t.Add(time.Hour * 22 * 7)

    // Prints output
    fmt.Printf("%v\n", t)
    fmt.Printf("%v\n", d1)
    fmt.Printf("%v\n", d2)
    fmt.Printf("%v\n", d3)
    fmt.Printf("%v", d4)
}
```

发帖主题：Re：Колибри0.7.8.0

这里，返回的输出采用上面定义的 UTC 格式。