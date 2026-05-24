# 如何比较格朗的时间？

> 原文:[https://www . geesforgeks . org/how-to-to-compare-time-in-golang/](https://www.geeksforgeeks.org/how-to-compare-times-in-golang/)

借助`**Before()**`和`**After()**`以及`**Equal()**`功能，我们可以比较时间和日期，但是我们也将使用`**time.Now()**`和`**time.Now().Add()**`功能进行比较。

**使用的功能:**这些功能将时间与*秒*进行比较。

*   `Before(temp)`–该函数用于检查给定时间是否在临时时间变量之前，如果时间变量在临时时间变量之前，则返回 true，否则返回 false。
*   `After(temp)`–该函数用于检查给定时间是否在临时时间变量之后，如果时间变量在临时时间变量之后，则返回 true，否则返回 false。
*   `Equal(temp)`–该函数用于检查给定时间是否等于临时时间变量，如果时间变量等于临时时间变量则返回真，否则返回假。

**示例#1 :** 在这个示例中，我们可以看到，通过使用`Before()`和`After()`函数，我们可以使用这些函数来比较日期。

```go
// Golang program to compare times
package main

import "fmt"

// importing time module
import "time"

// Main function
func main() {

    today := time.Now()
    tomorrow := today.Add(24 * time.Hour)

    // Using time.Before() method
    g1 := today.Before(tomorrow)
    fmt.Println("today before tomorrow:", g1)

    // Using time.After() method
    g2 := tomorrow.After(today)
    fmt.Println("tomorrow after today:", g2)

}
```

**输出:**

```go
today before tomorrow: true
tomorrow after today: true

```

**例 2 :**

```go
// Golang program to compare times
package main

import "fmt"

// importing time module
import "time"

// Main function
func main() {

    today := time.Now()
    tomorrow := today.Add(24 * time.Hour)
    sameday := tomorrow.Add(-24 * time.Hour)

    if today != tomorrow {
        fmt.Println("today is not tomorrow")
    }

    if sameday == today {
        fmt.Println("sameday is today")
    }

    // using Equal function
    if today.Equal(sameday) {
        fmt.Println("today is sameday")
    }

}
```

**输出:**

```go
today is not tomorrow
sameday is today
today is sameday

```