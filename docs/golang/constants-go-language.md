# 常量- Go 语言

> 原文:[https://www.geeksforgeeks.org/constants-go-language/](https://www.geeksforgeeks.org/constants-go-language/)

顾名思义**CONTENTS**的意思是固定的，在编程语言中也是一样的，即一旦定义了常量的值，就不能再修改了。可以有任何基本的常量数据类型，如整数常量、浮点常量、字符常量或字符串。

**如何申报？**
常量是像变量一样声明的，但是在使用 ***常量*** 关键字作为前缀来声明具有特定类型的常量时。不能使用 **:=** 语法声明。

**示例:**

## 去

```go
package main

import "fmt"

const PI = 3.14

func main()
{
    const GFG = "GeeksforGeeks"
    fmt.Println("Hello", GFG)

    fmt.Println("Happy", PI, "Day")

    const Correct= true
    fmt.Println("Go rules?", Correct)
}
```

**输出:**

```go
Hello GeeksforGeeks
Happy 3.14 Day
Go rules? true
```

**非类型化和类型化数值常量:**
类型化常量的工作方式类似于不可变变量只能与同一类型相互操作，非类型化常量的工作方式类似于文字可以与相似类型相互操作。常量可以在 Go 中声明，也可以不声明类型。下面的示例显示了已命名和未命名的类型化和非类型化数值常量。

```go
const untypedInteger          = 123
const untypedFloating typed   = 123.12

const typedInteger  int             = 123
const typedFloatingPoint   float64  = 123.12
```

**以下是 Go 语言中的常量列表:**

*   数字常数(整数常数、浮点常数、复数常数)
*   字符串文字
*   布尔常数

**数值常量:**
数值常量为 ***高精度值*** 。As Go 是一种静态类型的语言，不允许混合数字类型的操作。您不能将 ***float64*** 添加到 ***int*** 中，甚至不能将***int 32*****添加到 ***int*** 中。虽然，写***1e 6 *时间是合法的。第二*** 或 ***数学。Exp(1)*** 甚至***1<<(' \ t '+2.0)***。在围棋中，常数与变量不同，表现得像正则数。**

**数字常量可以有三种，即整数、浮点、复数**

****整数常数:****

*   **前缀指定基数或基数:0x 或 0X 表示十六进制，0 表示八进制，零表示十进制。**
*   **整数文字也可以有一个*后缀*，它是 U(大写)和 L(大写)的组合，分别表示无符号和长整型**
*   **它可以是十进制、八进制或十六进制常量。**
*   **int 最多可以存储 64 位整数，有时更少。**

**以下是*整数常数的一些例子:***

```go
85         /* decimal */
0213       /* octal */
0x4b       /* hexadecimal */
30         /* int */
30u        /* unsigned int */
30l        /* long */
30ul       /* unsigned long */
212         /* Legal */
215u        /* Legal */
0xFeeL      /* Legal */
078         /* Illegal: 8 is not an octal digit */
032UU       /* Illegal: cannot repeat a suffix */
```

****复常数:**
复常数的行为很像浮点常数。它是整数常量(或参数)的*有序对*或*实数对*，常量之间用逗号隔开，该对用括号括起来。第一个常数是实部，第二个是虚部。复数常量 COMPLEX*8 使用 *8 字节*的存储空间。**

****示例:****

```go
(0.0, 0.0) (-123.456E+30, 987.654E-29)
```

****浮动式常数:****

*   **浮点型常数有一个*整数部分、一个小数点、一个小数部分和一个指数部分*。**
*   **可以用十进制或指数形式表示浮动常数。**
*   ***当*用十进制形式表示时，必须包括小数点、指数或两者。**
*   **当使用*指数*形式表示时，必须包括整数部分、小数部分或两者。**

**以下是浮点型常量的示例:**

```go
3.14159       /* Legal */
314159E-5L    /* Legal */
510E          /* Illegal: incomplete exponent */
210f          /* Illegal: no decimal or exponent */
.e55          /* Illegal: missing integer or fraction */
```

****字符串文字****

*   **Go 支持两种类型的字符串文字，即" "(双引号样式)和" "(反引号)。**
*   **字符串可以用 **+** 和 **+=** 运算符连接*。***
*   **字符串包含类似于字符文字的字符:普通字符、转义序列和通用字符。这是没有打字的。**
*   **字符串类型的零值为空字符串，可以用文字上的**“**”或**“**表示。**
*   **字符串类型都可以用 **==，！=** 和(用于相同类型的比较)**

****语法****

```go
type _string struct {
    elements *byte // underlying bytes
    len      int   // number of bytes
}
```

****显示字符串文字的示例:****

```go
"hello, geeksforgeeks" 

"hello, \ 

geeksforgeeks" 

"hello, " "geeks" "forgeeks" 
```

**这里，以上三种说法都是相似的，即没有任何特定的类型。**

****示例:****

## **去**

```go
package main

import "fmt"

func main()
{
    const A = "GFG"
    var B = "GeeksforGeeks"

    // Concat strings.
    var helloWorld = A+ " " + B
    helloWorld += "!"
    fmt.Println(helloWorld)

    // Compare strings.
    fmt.Println(A == "GFG")  
    fmt.Println(B < A)
}
```

****输出:****

```go
GFG GeeksforGeeks!
true
false
```

****布尔常量:**
布尔常量类似于字符串常量。它应用与字符串常量相同的规则。区别只是它有两个非类型化的常量真和假。**

## **去**

```go
package main

import "fmt"

const Pi = 3.14

func main()
{
    const trueConst = true

    // Type definition using type keyword
    type myBool bool   
    var defaultBool = trueConst // allowed
    var customBool myBool = trueConst // allowed

    //  defaultBool = customBool // not allowed
    fmt.Println(defaultBool)
    fmt.Println(customBool)  
}
```

****输出:****

```go
true
true
```