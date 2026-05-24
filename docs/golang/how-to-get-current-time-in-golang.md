# 如何获取格朗当前时间？

> 原文:[https://www . geeksforgeeks . org/如何获取当前时间在 golang/](https://www.geeksforgeeks.org/how-to-get-current-time-in-golang/)

借助`**time.Now()**`功能，我们可以通过导入时间模块得到当前在 Golang 的时间。

> **语法:** `time.Now()`
> **返回:**返回当前日期和时间。

**示例#1:** 在这个示例中，我们可以看到，通过使用`time.Now()`函数，我们能够获得当前的日期和时间。

```go
// Golang program to get the current time
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// importing time module
import "time"

// Main function
func main() {

    // Using time.Now() function.
    dt := time.Now()
    fmt.Println("Current date and time is: ", dt.String())
}
```

**输出:**

```go
Current date and time is:  2009-11-10 23:00:00 +0000 UTC m=+0.000000001

```

**例 2:**

```go
// Golang program to get the current time
package main

// Here "fmt" is formatted IO which
// is same as C’s printf and scanf.
import "fmt"

// importing time module
import "time"

// Main function
func main() {

    // Using time.Now() function.
    dt := time.Now()
    fmt.Println(dt.Format("01-02-2006 15:04:05"))

}
```

**输出:**

```go
11-10-2009 23:00:00

```