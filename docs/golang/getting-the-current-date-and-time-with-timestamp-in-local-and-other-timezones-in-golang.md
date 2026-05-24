# 获取当前日期和时间，并在 Golang 的本地和其他时区加上时间戳

> 原文:[https://www . geesforgeks . org/get-当前日期和时间-带时间戳的本地和其他时区-in-golang/](https://www.geeksforgeeks.org/getting-the-current-date-and-time-with-timestamp-in-local-and-other-timezones-in-golang/)

借助 **Location()** 功能，我们可以在本地获取带有时间戳的当前日期和时间，借助 **LoadLocation()** 功能，我们可以获取 Golang 的其他时区。LoadLocation()将字符串(城市名)作为参数，并返回地点。
。location()不带参数，返回 location .time.now()返回当前日期和时间，并在 local 中加上时间戳。

**1。location()** :不带参数，返回本地时间。

**2。func LoadLocation(名称字符串)(*Location，错误)**:它将地名作为参数。返回给定名称的位置或返回零作为错误。

**3。时间到了。Now()** :返回当前时间。

**例 1:**

```go
package main

import (
    "fmt"
    "time"
)

//main function
func main() {

    // with the help of time.Now()
    // store the local time
    t := time.Now()

    // print location and local time
    fmt.Println("Location : ", t.Location(), " Time : ", t)
}
```

**输出:**

```go
Location :  Local  Time :  2009-11-10 23:00:00 +0000 UTC m=+0.000000001

```

**例 2:**

```go
package main

import (
    "fmt"
    "time"
)

// main function
func main() {

    // with the help of time.Now() 
    // store the local time
    t := time.Now()

    // print location and local time
    location, err := time.LoadLocation("America/New_York")
    if err != nil {
        fmt.Println(err)
    }

    // America/New_York
    fmt.Println("Location : ", location, " Time : ", t.In(location)) 
}
```

**输出:**

```go
Location :  America/New_York  Time :  2009-11-10 18:00:00 -0500 EST

```