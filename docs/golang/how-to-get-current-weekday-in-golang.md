# 如何获取 Golang 当前工作日？

> 原文:[https://www . geesforgeks . org/如何获取当前工作日在 golang/](https://www.geeksforgeeks.org/how-to-get-current-weekday-in-golang/)

借助`**time.Now().Weekday()**`功能，我们可以通过导入时间模块得到 Golang 中的工作日。

> **语法:** `time.Now().Weekday()`
> **返回:**返回当前工作日。

**示例#1:** 在这个示例中，我们可以看到通过使用`time.Now().Weekday()`函数，我们能够得到工作日。

```go
// Golang program to get the current weekday
package main

// Here "fmt" is formatted IO which 
// is same as C’s printf and scanf.
import "fmt"

// importing time module
import "time"

// Main function
func main() {

    // Using time.Now().Weekday() function.
    dt := time.Now().Weekday()
    fmt.Println(dt.String())
}
```

**输出:**

```go
Monday

```

**例 2:**

```go
// Golang program to get the current weekday
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// importing time module
import "time"

// Main function
func main() {

    // Using time.Now().Weekday() function
    dt := time.Now().Weekday()
    fmt.Println(int(dt))

}
```

**输出:**

```go
1

```