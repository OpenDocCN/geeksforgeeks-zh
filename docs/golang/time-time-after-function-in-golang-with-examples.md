# Golang 中的 time.Time.After()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-after-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-after-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 围棋语言中的**Time.After()**函数用于检查所述时刻 t 是否在所述 u 之后。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) After(u Time) bool

```

这里，“t”是指定的时间，“u”是作为参数出现在 After()方法中的时间。

**返回值：**如果“u”后有“t”，则返回 TRUE，否则返回 FALSE。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.After() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t and u in UTC
    t := time.Date(2020, 0, 0, 0, 0, 0, 0, time.UTC)
    u := time.Date(2019, 0, 0, 0, 0, 0, 0, time.UTC)

    // Calling After method
    res := t.After(u)

    // Prints output
    fmt.Printf("%v", res)
}
```

发帖主题：Re：Колибри0.7.0

```go
true

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.After() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t and u in UTC
    t := time.Date(2030, 0, 0, 0, 0, 0, 0, time.UTC)
    u := time.Date(2040, 0, 0, 0, 0, 0, 0, time.UTC)

    // Calling After method
    res := t.After(u)

    // Prints output
    fmt.Printf("%v", res)
}
```

发帖主题：Re：Колибри0.7.0

```go
false

```