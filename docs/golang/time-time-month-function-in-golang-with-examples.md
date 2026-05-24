# Golang 中的 time.Time.Month()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-month-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-month-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**Time.Month()**函数用于查找 t 提供的一年中的哪个月。此外，该函数在时间包中定义。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func (t Time) Month() Month

```

这里，“t”是规定的时间。

**返回值：**返回“t”提供的一年中的月份。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Month() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2019, 6, 5,
       11, 51, 04, 0, time.UTC)

    // Calling Month method
    month := t.Month()

    // Prints month as specified
    fmt.Printf("The stated month of the"+
      " year specified is: %v\n", month)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Month() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2019, 23, 5,
        11, 51, 04, 0, time.UTC)

    // Calling Month method
    month := t.Month()

    // Prints month as specified
    fmt.Printf("The stated month of the "+
        "year specified is: %v\n", month)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面代码中以整数表示的月份超出了通常的范围，但它在转换时被标准化了。