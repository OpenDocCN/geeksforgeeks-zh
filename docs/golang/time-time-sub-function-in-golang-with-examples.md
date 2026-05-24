# Golang 中的 time.Time.Sub()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-sub-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-sub-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Sub()**函数用于生成通过执行操作 t-u 获得的持续时间。 如果这里的输出超过了可以存储在持续时间“d”中的最大或最小值，则将返回最大或最小持续时间。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

> **语法：**
> 
> ```go
> func (t Time) Sub(u Time) Duration
> 
> ```
> 
> 这里，“t”和“u”是规定的时间。
> 
> **注意：**要计算给定持续时间“d”的“t-d”，需要使用 t.Add(-d)。
> 
> **返回值：**返回 t-u 运算得到的时长。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Sub() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining t and u for Sub method
    t := time.Date(2020, 11, 14, 16,
               45, 16, 36, time.UTC)
    u := time.Date(2019, 9, 5, 18, 0,
                      0, 0, time.UTC)

    // Calling Sub method
    subtract := t.Sub(u)

    // Prints output
    fmt.Printf("t-d = %v\n", subtract)
}
```

发帖主题：Re：Колибри0.7.0

```go
t-d = 10462h45m16.000000036s

```

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Sub() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Defining t and u for Sub method
    t := time.Date(2020, 11, 14, 34, 
               67, 98, 63, time.UTC)
    u := time.Date(2019, 9, 5, 28, 
            66, 89, 100, time.UTC)

    // Calling Sub method
    subtract := t.Sub(u)

    // Prints output
    fmt.Printf("t-d = %v\n", subtract)
}
```

发帖主题：Re：Колибри0.7.0

```go
t-d = 10470h1m8.999999963s

```

在这里，上面代码中声明的时间“t”和“u”的值超出了通常的范围，但它们在转换时被标准化了。