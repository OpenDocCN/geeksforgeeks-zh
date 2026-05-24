# 用例子比较戈朗的 Println 和 Printf

> 原文:[https://www . geesforgeks . org/compare-println-vs-printf-in-golang-with-examples/](https://www.geeksforgeeks.org/compare-println-vs-printf-in-golang-with-examples/)

Println 和 Printf 是在 Golang 中打印输出的函数。两者都存在于包装“ **fmt** ”内。但是，这两个函数提供的输出不同，如下所示:

### 印本

表示“打印行”。它帮助我们打印整数、字符串等，但在末尾插入一个新行，即插入一个换行符。它使用操作数的默认格式来格式化字符串。Println 还在参数之间插入空格。

**语法:**

```go
func Println(a ...interface{}) (n int, err error)

```

**例 1:**

```go
// Golang program to show the uses of Println function
package main

import "fmt"

func main() {

    // The Println prints and
    // adds a new line
    s := "Sam"
    age := 25
    fmt.Println("His name is", s)

    fmt.Println("His age is", age, "years")
}
```

**输出:**

```go
His name is Sam
His age is 25 years

```

**例 2:**

```go
// Golang program to show the uses of Println function
package main

import "fmt"

func main() {
    a, b := 10, 20

    fmt.Println("a * b: ")
    fmt.Println(a, "*", b, "=", a*b)
}
```

**输出:**

```go
a * b: 
10 * 20 = 200

```

### 打印函数

表示“打印格式器”。它打印格式化的字符串。它包含您想要打印的字符串中的符号，然后它后面的参数将替换这些符号点。它不会像 Println 那样在末尾插入新行。为此，您必须在最后添加“\n”。它根据格式说明符格式化字符串。

**语法:**

```go
func Printf(format string, a ...interface{}) (n int, err error)

```

**例 1:**

```go
// Golang program to show the uses of Printf function
package main

import "fmt"

func main() {

    // The Printf prints but
    // doesn't add a new line
    s := "Sam"
    age := 25

    fmt.Printf("His name is %s", s)

    fmt.Printf("His age is %d ", age)
    fmt.Printf("years")
}
```

**输出:**

```go
His name is SamHis age is 25 years

```

为了更清楚，请看下面的例子。**这里 Printf 根据指定的格式说明符进行格式化，但是 Println 使用其操作数的默认格式。**

```go
// Golang program to show the uses
// of Printf and Println function
package main

import "fmt"

func main() {
    m, n, p := 15, 25, 40

    fmt.Println(
        "(m + n = p) :", m, "+", n, "=", p,
    )

    fmt.Printf(
        "(m + n = p) : %d + %d = %d\n", m, n, p,
    )
}
```

**输出:**

```go
(m + n = p) : 15 + 25 = 40
(m + n = p) : 15 + 25 = 40

```