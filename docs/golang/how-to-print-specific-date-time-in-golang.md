# 如何在 Golang 打印具体日期时间？

> 原文:[https://www . geesforgeks . org/how-to-print-special-date-time-in-golang/](https://www.geeksforgeeks.org/how-to-print-specific-date-time-in-golang/)

Golang 通过基于模式的布局支持时间格式化和解析。在围棋中，当前时间可以通过使用**时间来确定。现在()**，由时间包提供。包装时间提供测量和显示时间的功能。

要打印**当前的**日期时间，您需要在您的 Go 程序中导入[“时间”](https://golang.org/pkg/time/)包来处理日期和时间。

**示例:**

```go
// Golang program to show
// the use of time.Now() Function
package main

import "fmt"
import "time"

func main() {
    dt := time.Now()

    // printing the time in string format
    fmt.Println("Current date and time is: ", dt.String())
}
```

**输出:**

```go
Current date and time is:  2020-05-05 06:43:01.419199824 +0000 UTC m=+0.000076701
```

要在 Golang 中打印**特定的**日期时间，请使用时间包中提供的格式常数。常用的格式有:

```go
const (
    ANSIC       = "Mon Jan _2 15:04:05 2006"
    UnixDate    = "Mon Jan _2 15:04:05 MST 2006"
    RubyDate    = "Mon Jan 02 15:04:05 -0700 2006"
    RFC822      = "02 Jan 06 15:04 MST"
    RFC822Z     = "02 Jan 06 15:04 -0700" // RFC822 with numeric zone
    RFC850      = "Monday, 02-Jan-06 15:04:05 MST"
    RFC1123     = "Mon, 02 Jan 2006 15:04:05 MST"
    RFC1123Z    = "Mon, 02 Jan 2006 15:04:05 -0700" // RFC1123 with numeric zone
    RFC3339     = "2006-01-02T15:04:05Z07:00"
    RFC3339Nano = "2006-01-02T15:04:05.999999999Z07:00"
    Kitchen     = "3:04PM"
    // Handy time stamps.
    Stamp      = "Jan _2 15:04:05"
    StampMilli = "Jan _2 15:04:05.000"
    StampMicro = "Jan _2 15:04:05.000000"
    StampNano  = "Jan _2 15:04:05.000000000"
)

```

**示例:**

```go
// Golang program to print specific date and time
package main

import "fmt"
import "time"

func main() {

    dt := time.Now()

    // printing date and time in UnixDate format
    fmt.Println("Specific date and time is: ", dt.Format(time.UnixDate))
}
```

**输出:**

```go
Specific date and time is:  Tue May  5 07:05:00 UTC 2020

```

**示例:**

```go
// Golang program to print specific date and time
package main

import "fmt"
import "time"

func main() {
    dt := time.Now()

    // Format MM-DD-YYYY
    fmt.Println(dt.Format("01-02-2006"))

    // Format MM-DD-YYYY hh:mm:ss
    fmt.Println(dt.Format("01-02-2006 15:04:05"))

    // With short weekday (Mon)
    fmt.Println(dt.Format("01-02-2006 15:04:05 Mon"))

    // With weekday (Monday)
    fmt.Println(dt.Format("01-02-2006 15:04:05 Monday"))

    // Include micro seconds
    fmt.Println(dt.Format("01-02-2006 15:04:05.000000"))
}
```

**输出:**

```go
11-10-2009
11-10-2009 23:00:00
11-10-2009 23:00:00 Tue
11-10-2009 23:00:00 Tuesday
11-10-2009 23:00:00.000000

```