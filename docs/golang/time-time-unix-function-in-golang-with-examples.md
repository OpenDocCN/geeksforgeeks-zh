# Golang 中的 time.Time.Unix()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-unix-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-unix-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Unix()**函数用于将“t”作为 Unix 时间(即从 1970 年 1 月 1 日起经过的秒数，以 UTC 表示)，此处的输出不依赖于与 t 相关的位置。此外，该函数在时间包中定义。 在这里，您需要导入“time”包才能使用这些函数。

> **语法：**
> 
> ```go
> func (t Time) Unix() int64
> 
> ```
> 
> 这里，“t”是规定的时间。
> 
> **注意：**类 Unix 操作系统经常将时间存储为 32 位秒数。 另一方面，这里的 unix()方法返回一个 64 位的值，因此它的有效期是数十亿年的过去或未来。
> 
> **返回值：**它返回“t”作为 Unix 时间，类型为 int64。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Unix() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t in UTC for Unix method
    t := time.Date(2020, 11, 14, 11, 30, 32, 0, time.UTC)

    // Calling Unix method
    unix := t.Unix()

    // Prints output
    fmt.Printf("%v\n", unix)
}
```

发帖主题：Re：Колибри0.7.0

```go
1605353432

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Unix() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t in UTC for Unix method
    t := time.Date(2013, 11, 14, 1e3, 3e5, 7e1, 0, time.UTC)

    // Calling Unix method
    unix := t.Unix()

    // Prints output
    fmt.Printf("%v\n", unix)
}
```

发帖主题：Re：Колибри0.7.0

```go
1405987270

```

这里，上述代码中所述的时间“t”具有包含常量“e”的值，这些常量在转换时在通常范围内转换。