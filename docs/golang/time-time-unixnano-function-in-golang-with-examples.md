# Golang 中的 time.Time.UnixNano()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-unixnano-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-unixnano-function-in-golang-with-examples/)

在围棋语言中，*Time*包提供了确定和查看时间的功能。 GO 语言中的**Time.UnixNano()**函数用于将“t”作为 Unix 时间(即从 1970 年 1 月 1 日起经过的秒数，以 UTC 表示)，此处的输出不依赖于与 t 相关的位置。此外，该函数在时间包中定义。 在这里，您需要导入“time”包才能使用这些函数。

> **语法：**
> 
> ```go
> func (t Time) UnixNano() int64
> ```
> 
> 这里，“t”是规定的时间。
> **注意：**在这里，如果给定的 Unix 时间(以纳秒为单位)不是由 int64 类型形成的(它是 1678 年之前或 2262 年之后的日期)，则不定义返回的输出。 这意味着在零时间调用 UnixNano()方法的结果是不明确的。
> **返回值：**它返回“t”作为类型为 int64 的 Unix 时间。

**示例 1：**

## 行走 / 离开 / 变成 / 走

```go
// Golang program to illustrate the usage of
// Time.UnixNano() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t in UTC
    // for UnixNano method
    t := time.Date(2019, 13, 15, 23,
               90, 12, 04, time.UTC)

    // Calling UnixNano method
    unixnano := t.UnixNano()

    // Prints output
    fmt.Printf("%v\n", unixnano)
}
```