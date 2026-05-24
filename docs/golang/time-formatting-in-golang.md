# 以 Golang

为单位的时间格式

> Original: [https://www.geeksforgeeks.org/time-formatting-in-golang/](https://www.geeksforgeeks.org/time-formatting-in-golang/)

Golang 通过基于模式的布局支持时间格式化和解析。 要格式化时间，我们使用**format()**方法，该方法格式化*time.Time*对象。

**语法：**

```go
func (t Time) Format(layout string) string
```

我们可以提供自定义格式，也可以提供预定义的日期和时间戳格式常量，如下所示。

| 安排 / 设计 / 样式 / 格式 | 例证 / 范例 / 榜样 / 例子 |
| ANSIC | Mon，Jan_2 15：05：05 2006 |
| UnixDate | Mon，Jan_2 15：05：05 MST 2006 |
| RubyDate | “Mon Jan 02 15：05：05-0700 2006” |
| RFC822。 | “02 Jan 06 15：04 MST” |
| RFC822Z | ==同步，由 Elderman 更正==@ELDER_MAN |
| 是 RF550。 | MST，星期一，02-01-06 15：04：05 |
| RFC-123。 | “Mon，01,2006 15：04：05 MST” |
| RFC1123Z | "蒙, 2006 年 1 月 02 日 15 : 05-0700 " |
| RFC 3339 | “2006-01-02T15：04：05Z07：00” |
| RFC3339 纳米 | “2006-01-02T15：04：05.99999999Z07：00” |

布局必须使用参考时间 Mon Jan 2 15：04：05 MST 2006 来显示格式化/解析给定时间/字符串的模式。

**示例 1：**

```go
// Golang program to illustrate the time
// formatting using custom layouts

package main

import (
    "fmt"
    "time"
)

func main() {

    // this function returns the present time
    current_time := time.Now()

    // individual elements of time can
    // also be called to print accordingly
    fmt.Printf("%d-%02d-%02dT%02d:%02d:%02d-00:00\n",
    current_time.Year(), current_time.Month(), current_time.Day(),
    current_time.Hour(), current_time.Minute(), current_time.Second())

    // formatting time using
    // custom formats
    fmt.Println(current_time.Format("2006-01-02 15:04:05"))
    fmt.Println(current_time.Format("2006-January-02"))
    fmt.Println(current_time.Format("2006-01-02 3:4:5 pm"))
}
```

发帖主题：Re：Колибри0.7.0

```go
2009-11-10T23:00:00-00:00
2009-11-10 23:00:00
2009-November-10
2009-11-10 11:0:0 pm

```

**示例 2：**

```go
// Golang program to illustrate the time
// formatting using format constants
package main

import (
    "fmt"
    "time"
)

func main() {

    // this function returns the present time
    current_time := time.Now()

    // using inbuilt format constants
    // shown in the table above
    fmt.Println("ANSIC: ", current_time.Format(time.ANSIC))
    fmt.Println("UnixDate: ", current_time.Format(time.UnixDate))
    fmt.Println("RFC1123: ", current_time.Format(time.RFC1123))
    fmt.Println("RFC3339Nano: ", current_time.Format(time.RFC3339Nano))
    fmt.Println("RubyDate: ", current_time.Format(time.RubyDate))
}
```

发帖主题：Re：Колибри0.7.0

```go
ANSIC:  Tue Nov 10 23:00:00 2009
UnixDate:  Tue Nov 10 23:00:00 UTC 2009
RFC1123:  Tue, 10 Nov 2009 23:00:00 UTC
RFC3339Nano:  2009-11-10T23:00:00Z
RubyDate:  Tue Nov 10 23:00:00 +0000 2009

```