# 格朗解析时间

> 原文:[https://www.geeksforgeeks.org/parsing-time-in-golang/](https://www.geeksforgeeks.org/parsing-time-in-golang/)

解析时间就是把我们的时间转换成 Golang 时间对象，这样我们就可以轻松地从中提取日期、月份等信息。我们可以使用**时间解析任何时间。解析**函数，该函数将我们的时间字符串和我们的字符串写入的格式作为输入，如果我们的格式没有错误，它将返回一个 Golang 时间对象。

**例:**

```go
Input : "2018-04-24"
Output : 2018-04-24 00:00:00 +0000 UTC

Input : "04/08/2017"
Output : 2017-04-08 00:00:00 +0000 UTC

```

**代号:**

```go
// Golang program to show the parsing of time
package main

import (
    "fmt"
    "time"
)

func main() {

    // The date we're trying to 
    // parse, work with and format
    myDateString := "2018-01-20 04:35"
    fmt.Println("My Starting Date:\t", myDateString)

    // Parse the date string into Go's time object
    // The 1st param specifies the format,
    // 2nd is our date string
    myDate, err := time.Parse("2006-01-02 15:04", myDateString)
    if err != nil {
        panic(err)
    }

    // Format uses the same formatting style
    // as parse, or we can use a pre-made constant
    fmt.Println("My Date Reformatted:\t", myDate.Format(time.RFC822))

    // In YY-MM-DD
    fmt.Println("Just The Date:\t\t", myDate.Format("2006-01-02"))
}
```

**输出:**

```go
My Starting Date:     2018-01-20 04:35
My Date Reformatted:     20 Jan 18 04:35 UTC
Just The Date:         2018-01-20

```