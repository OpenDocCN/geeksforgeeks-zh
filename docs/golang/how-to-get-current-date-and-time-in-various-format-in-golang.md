# 如何在 Golang 获取各种格式的当前日期和时间？

> 原文:[https://www . geesforgeks . org/如何以各种格式获取当前日期和时间/golang/](https://www.geeksforgeeks.org/how-to-get-current-date-and-time-in-various-format-in-golang/)

Golang 中的包“**时间**”提供了测量和显示时间的功能。日历计算总是采用公历，没有闰秒。使用*“时间。现在()"*功能你可以得到*中的日期和时间“yyyy-mm-dd hh:mm:ss .毫秒时区”*格式。这是在 golang 获取日期和时间的最简单方法。

## 去

```go
// Golang program to get current date and time
package main

import (
    "fmt"
    "time"
)

func main() {

    // get date and time and store in variable on left
    currentTime := time.Now()

    // printing the date and time in string format
    fmt.Println("Current Time in String: ", currentTime.String())
}
```

**输出:**

```go
Current Time in String:  2009-11-10 23:00:00 +0000 UTC m=+0.000000001
```

**获取格式化的日期和时间:**使用您的时间变量或标识符上的*“Format()”*功能，您可以获得各种格式的输出，如下例所示。您需要在**“格式()”**功能中指定所需输出的格式。这是 Golang 编程中最灵活的日期和时间格式化方式之一。

**示例:**

## 去

```go
// Golang program to get the current
// date and time in various format
package main

import (
    "fmt"
    "time"
)

func main() {

    // using time.Now() function
    // to get the current time
    currentTime := time.Now()

    // getting the time in string format
    fmt.Println("Show Current Time in String: ", currentTime.String())

    fmt.Println("YYYY.MM.DD : ", currentTime.Format("2017.09.07 17:06:06"))

    fmt.Println("YYYY#MM#DD {Special Character} : ", currentTime.Format("2017#09#07"))

    fmt.Println("MM-DD-YYYY : ", currentTime.Format("09-07-2017"))

    fmt.Println("YYYY-MM-DD : ", currentTime.Format("2017-09-07"))

    fmt.Println("YYYY-MM-DD hh:mm:ss : ", currentTime.Format("2017-09-07 17:06:06"))

    fmt.Println("Time with MicroSeconds: ", currentTime.Format("2017-09-07 17:06:04.000000"))

    fmt.Println("Time with NanoSeconds: ", currentTime.Format("2017-09-07 17:06:04.000000000"))

    fmt.Println("ShortNum Width : ", currentTime.Format("2017-02-07"))

    fmt.Println("ShortYear : ", currentTime.Format("06-Feb-07"))

    fmt.Println("LongWeekDay : ", currentTime.Format("2017-09-07 17:06:06 Wednesday"))

    fmt.Println("ShortWeek Day : ", currentTime.Format("2017-09-07 Wed"))

    fmt.Println("ShortDay : ", currentTime.Format("Wed 2017-09-2"))

    fmt.Println("LongWidth : ", currentTime.Format("2017-March-07"))

    fmt.Println("ShortWidth : ", currentTime.Format("2017-Feb-07"))

    fmt.Println("Short Hour Minute Second: ", currentTime.Format("2017-09-07 2:3:5 PM"))

    fmt.Println("Short Hour Minute Second: ", currentTime.Format("2017-09-07 2:3:5 pm"))

    fmt.Println("Short Hour Minute Second: ", currentTime.Format("2017-09-07 2:3:5"))

}
```

**输出:**

```go
Show Current Time in String:  2009-11-10 23:00:00 +0000 UTC m=+0.000000001
YYYY.MM.DD :  10117.09.07 117:09:09
YYYY#MM#DD {Special Character} :  10117#09#07
MM-DD-YYYY :  09+00-10117
YYYY-MM-DD :  10117-09+00
YYYY-MM-DD hh:mm:ss :  10117-09+00 117:09:09
Time with MicroSeconds:  10117-09+00 117:09:00.000000
Time with NanoSeconds:  10117-09+00 117:09:00.000000000
ShortNum Width :  10117-10+00
ShortYear :  09-Feb+00
LongWeekDay :  10117-09+00 117:09:09 Wednesday
ShortWeek Day :  10117-09+00 Wed
ShortDay :  Wed 10117-09-10
LongWidth :  10117-March+00
ShortWidth :  10117-Feb+00
Short Hour Minute Second:  10117-09+00 10:11:0 PM
Short Hour Minute Second:  10117-09+00 10:11:0 pm
Short Hour Minute Second:  10117-09+00 10:11:0
```