# Golang 中的 time.Time.Year()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-time-year-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-time-year-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**Time.Year()**函数用于查找出现指定“t”的年份。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

> **语法：**
> 
> ```go
> func (t Time) Year() int
> 
> ```
> 
> 这里，“t”是规定的时间。
> 
> **返回值：**返回指定 t 出现的年份。

**示例 1：**

```go
// Golang program to illustrate the usage of
// Time.Year() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2019, 6, 5, 11, 
             35, 04, 0, time.UTC)

    // Calling Year method
    yr := t.Year()

    // Prints year as specified
    fmt.Printf("The stated year in the"+
          " 't' specified is: %v\n", yr)
}
```

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

```go
// Golang program to illustrate the usage of
// Time.Year() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring t in UTC
    t := time.Date(2019, 13, 35, 
       28, 89, 63, 0, time.UTC)

    // Calling Year method
    yr := t.Year()

    // Prints year as specified
    fmt.Printf("The stated year in the"+
         " 't' specified is: %v\n", yr)
}
```

发帖主题：Re：Колибри0.7.8.0

在这里，上面提到的“t”的值超出了通常的范围，但它们在转换时被标准化了。