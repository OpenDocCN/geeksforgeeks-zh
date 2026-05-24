# Golang 中的 time.Now()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-now-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-now-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**now()**函数用于查找当前本地时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func Now() Time

```

**返回值：**返回当前本地时间。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.Now() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling Now() method
    tm := time.Now()

    // Prints current 
    // local time in UTC
    fmt.Printf("%s", tm)
}
```

发帖主题：Re：Колибри0.7.0

```go
2020-04-09 11:24:14.785868848 +0000 UTC m=+0.000187421

```

在这里，当前时间以 UTC 为单位返回。

**示例 2：**

```go
// Golang program to illustrate the usage of
// time.Now() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Calling Now() method
    tm := time.Now()
    tm1 := time.Now()

    // Prints current local time in UTC
    fmt.Printf("%s\n", tm)

    // Sleep for 10 seconds
    time.Sleep(10 * time.Second)

    // Prints the current time after 10
    // seconds of the sleep is over
    fmt.Printf("%s", tm1)
}
```

发帖主题：Re：Колибри0.7.0

```go
2020-04-09 11:37:59.087484568 +0000 UTC m=+0.000106559
2020-04-09 11:37:59.087484779 +0000 UTC m=+0.000106736

```