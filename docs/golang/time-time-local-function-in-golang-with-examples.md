# Golang 中的 time.Time.Local()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-local-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-local-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Local()**函数用于查找位置设置为当地时间的“t”。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Local() Time

```

这里，“t”是规定的时间。

**返回值：**它返回“t”以及设置为本地时间的位置。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Local() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t parameter of Local method
    t := time.Date(2019, 2, 11, 10, 
              03, 00, 00, time.UTC)

    // Calling Local method
    local := t.Local()

    // Prints output
    fmt.Printf("%v\n", local)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Local() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining location using FixedZone method
    location := time.FixedZone("UTC-7", -6*56*34)

    // Defining t for calling Local method
    t := time.Date(2019, 2, 11, 10, 03, 00, 00, location)

    // Calling Local method
    local := t.Local()

    // Prints output
    fmt.Printf("%v\n", local)
}
```

发帖主题：Re：Колибри0.7.8.0

这里使用 FixedZone()方法来定义 date()方法的 location 参数，以便根据该位置返回输出中的时间。