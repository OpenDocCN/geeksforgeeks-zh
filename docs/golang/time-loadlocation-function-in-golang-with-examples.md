# Golang 中的 time.LoadLocation()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-loadlocation-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-loadlocation-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 GO 语言中的**LoadLocation()**函数用于查找指定名称的位置。 因此，如果声明的名称是“UTC”，则返回*UTC*，如果声明的名称是“Local”，则返回*Local*。 否则，假定要使用的名称是相当于 IANA 时区数据库中的文件的位置。 其中此数据库仅存在于 Unix 系统上。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些函数。

**语法：**

```go
func LoadLocation(name string) (*Location, error)

```

这里，“name”是要使用的位置的名称，*location 是指向该位置的指针。 其中“位置”形成使用中的时间偏移量集合。 而“错误”是恐慌性错误。

**返回值：**返回指定名称的位置。

**示例 1：**

```go
// Golang program to illustrate the usage of
// LoadLocation() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Calling LoadLocation
    // method with its parameter
    locat, error := time.LoadLocation("Asia/Kolkata")

    // If error not equal to nil then
    // return panic error
    if error != nil {
        panic(error)
    }

    // Prints location
    fmt.Println(locat)
}
```

发帖主题：Re：Колибри0.7.8.0

这里返回的是印度的 IANA 时区，因为没有错误。

**示例 2：**

```go
// Golang program to illustrate the usage of
// LoadLocation() function

// Including main package
package main

// Importing fmt and time
import (
    "fmt"
    "time"
)

// Calling main
func main() {

    // Calling LoadLocation 
    // method with its parameter
    locat, error := time.LoadLocation("Asia/Kolkata")

    // If error not 
    // equal to nil then
    // return panic error
    if error != nil {
        panic(error)
    }

    // Calling Date() method 
    // with its parameter
    tm := time.Date(2020, 4, 7, 16,
                 7, 0, 0, time.UTC)

    // Prints the time and date
    // of the stated location
    fmt.Println(tm.In(locat))
}
```

发帖主题：Re：Колибри0.7.8.0

这里，首先调用 LoadLocation()方法，然后调用 date()方法及其参数，即日期和时间，然后返回指定位置的日期和时间。