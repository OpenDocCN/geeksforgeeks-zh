# Golang 中的 time.Time.IsZero()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-iszero-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-iszero-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.IsZero()**函数用于检查所述时间“t”是否表示零时间瞬间，例如，1，00：00：00 UTC 年 1 月 1 日。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func (t Time) IsZero() bool

```

这里，“t”是规定的时间。

**返回值：**如果指定的时间表示零时间瞬间，则返回 TRUE，否则返回 FALSE。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.IsZero() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t parameter of IsZero method
    t := time.Date(0001, 1, 1, 00, 00, 00, 00, time.UTC)

    // Calling IsZero method
    IsZeroOrnot := t.IsZero()

    // Prints output
    fmt.Printf("%v\n", IsZeroOrnot)
}
```

发帖主题：Re：Колибри0.7.0

```go
true

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.IsZero() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Defining t parameter 
    // of IsZero method
    t := time.Date(0001, 2, 1, 00, 
             00, 00, 00, time.UTC)

    // Calling IsZero method
    IsZeroOrnot := t.IsZero()

    // Prints output
    fmt.Printf("%v\n", IsZeroOrnot)
}
```

发帖主题：Re：Колибри0.7.0

```go
false

```