# fmt。Golang 中的 Printf()函数示例

> 原文:[https://www . geesforgeks . org/fmt-printf-function-in-golang-with-examples/](https://www.geeksforgeeks.org/fmt-printf-function-in-golang-with-examples/)

在 Go 语言中， *fmt* 包实现了格式化的输入输出，其功能类似于 C 的 printf()和 scanf()函数。 **fmt。Printf()** 函数在 Go 语言中根据格式说明符格式化并写入标准输出。此外，该功能在 fmt 包中定义。在这里，您需要导入“fmt”包才能使用这些功能。

**语法:**

```go
func Printf(format string, a ...interface{}) (n int, err error)
```

**参数:**该函数接受两个参数，如下图所示:

*   **格式字符串:**这个包含一些字符串和一些动词。
*   **a…接口{}:** 这包含指定的常量变量。

**返回值:**返回写入的字节数和遇到的任何写入错误。

**转换字符:**

<figure class="table">

| 转换字符 | 描述 |
| --- | --- |
| %b | 它用于格式化基数为 2 的数字 |
| %o | 它用于格式化基数为 8 的数字 |
| %O | 它用于格式化前缀为 0o 的 8 进制数字 |
| %d | 它用于格式化以小写字母 a-f 为基数的 10 个数字 |
| %x | 它被用来格式化十六进制数字，大写字母代表字母 A-F |
| %X | 它用于格式化 16 进制数字 |
| %g | 它用于格式化浮点值 |
| %s | 它用于格式化字符串值 |
| %t | 它用于格式化真值或假值 |
| %e | 它被用来格式化科学价值 |

</figure>

**例 1:**

## 去

```go
// Golang program to illustrate the usage of
// fmt.Printf() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some const variables
    const name, dept = "GeeksforGeeks", "CS"

    // Calling Printf() function
    fmt.Printf("%s is a %s Portal.\n", name, dept)

    // It is conventional not to worry about any
    // error returned by Printf.

}
```

**输出:**

```go
GeeksforGeeks is a CS portal.
```

**例 2:**

## 去

```go
// Golang program to illustrate the usage of
// fmt.Printf() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main() {

    // Declaring some const variables
    const num1, num2, num3 = 5, 10, 15

    // Calling Printf() function
    fmt.Printf("%d + %d = %d\n", num1, num2, num3)

    // It is conventional not to worry about any
    // error returned by Printf.

}
```

**输出:**

```go
5 + 10 = 15
```

**例 3:**

## 去

```go
// Golang program to illustrate the usage of
// fmt.Printf() function

// Including the main package
package main

// Importing fmt
import (
    "fmt"
)

// Calling main
func main(){

    var str = "Geeksforgeeks"
      fmt.Printf("The string is %s \n", str)
    var num1 int = 21
      fmt.Printf("The decimal value is %d \n", num1)
    var num2 float32 = 7.786
      fmt.Printf("The floating point is %g \n", num2)
    var num3 int = 14
      fmt.Printf("The binary value of num3 is %b \n", num3)
    var num4 = 4 + 1i
    fmt.Printf("Scientific Notation of num4 : %e \n", num4)
}
```

**输出:**

```go
The string is Geeksforgeeks  
The decimal value is 21  
The floating point is 7.786  
The binary value of num3 is 1110  
Scientific Notation of num4 : (4.000000e+00+1.000000e+00i)
```