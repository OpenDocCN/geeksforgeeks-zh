# Golang 中的 time.parse()函数，示例为

> Original: [https://www.geeksforgeeks.org/time-parse-function-in-golang-with-examples/](https://www.geeksforgeeks.org/time-parse-function-in-golang-with-examples/)

在围棋语言中，*Time*Packages 提供了确定和查看时间的功能。 Go 语言中的**parse()**函数用于解析格式化的字符串，然后找到它形成的时间值。 而且，这个函数是在时间包中定义的。 在这里，您需要导入“time”包才能使用这些功能。

**语法：**

```go
func Parse(layout, value string) (Time, error)

```

这里，布局通过显示参考时间(定义为**Mon Jan 2 15：04：05-0700 MST 2006**)的方式指定格式，如果它是值的话。 然而，先前定义的布局(如 UnixDate、ANSIC、RFC3339 等)解释了标准以及参考时间的适当表示。 而 value 参数保存字符串。 其中，从值中移除的元素被假定为零，当不可能为零时，则假定其为 1。

**返回值：**返回它表示的时间值。 如果时区指示符不存在，则返回以 UTC 为单位的时间。

**示例 1：**

```go
// Golang program to illustrate the usage of
// time.Parse() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring layout constant
    const layout = "Jan 2, 2006 at 3:04pm (MST)"

    // Calling Parse() method with its parameters
    tm, _ := time.Parse(layout, "Feb 4, 2014 at 6:05pm (PST)")

    // Returns output
    fmt.Println(tm)
}
```

发帖主题：Re：Колибри0.7.8.0

这里，返回的输出是上面定义的 PST 格式，这里使用的布局常量和值是它的长格式。

**示例 2：**

```go
// Golang program to illustrate the usage of
// time.Parse() function

// Including main package
package main

// Importing fmt and time
import "fmt"
import "time"

// Calling main
func main() {

    // Declaring layout constant
    const layout = "2006-Jan-02"

    // Calling Parse() method with its parameters
    tm, _ := time.Parse(layout, "2014-Feb-04")

    // Returns output
    fmt.Println(tm)
}
```

发帖主题：Re：Колибри0.7.8.0

这里，返回的输出是 UTC，因为没有时区指示符，这里使用的布局常量和值是它的缩写形式。