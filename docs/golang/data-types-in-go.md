# Go 中的数据类型

> 原文:[https://www.geeksforgeeks.org/data-types-in-go/](https://www.geeksforgeeks.org/data-types-in-go/)

数据类型指定有效的 [Go 变量](https://www.geeksforgeeks.org/go-variables/)可以保存的数据类型。在 Go 语言中，类型分为以下四类:

1.  **基本类型:**数字、字符串和布尔值都属于这一类。
2.  **聚合类型:**数组和结构属于这一类。
3.  **引用类型:**指针、切片、映射、函数和通道都属于这一类。
4.  **界面类型**

在这里，我们将讨论 Go 语言中的*基本数据类型*。 ***基础数据类型*** 进一步分为三个子类别:

*   **数字**
*   **布尔人**
*   **琴弦**

#### 数字

在围棋语言中，数字被分为三个子类别:

*   **整数:**在 Go 语言中，有符号和无符号整数都有四种不同的大小，如下表所示。有符号的 int 由 int 表示，无符号的整数由 uint 表示。

<figure class="table">

| 

数据类型

 | 

描述

 |
| --- | --- |
| **int8** | 8 位有符号整数 |
| **int16** | 16 位有符号整数 |
| **int32** | 32 位有符号整数 |
| **int64** | 64 位有符号整数 |
| uint 8 | 8 位无符号整数 |
| uint 16 | 16 位无符号整数 |
| **uint32** | 32 位无符号整数 |
| **uint64** | 64 位无符号整数 |
| **int** | in 和 uint 都包含相同的大小，32 位或 64 位。 |
| uint | in 和 uint 都包含相同的大小，32 位或 64 位。 |
| **符文** | 它是 int32 的同义词，也代表 Unicode 代码点。 |
| **字节** | 它是 int8 的同义词。 |
| **【uintptr】** | 它是无符号整数类型。它的宽度没有定义，但它可以容纳指针值的所有位。 |

</figure>

**示例:**

## 去

```go
// Go program to illustrate
// the use of integers
package main
import "fmt"

func main() {

    // Using 8-bit unsigned int
    var X uint8 = 225
    fmt.Println(X, X-3)

    // Using 16-bit signed int
    var Y int16 = 32767
    fmt.Println(Y+2, Y-2)
}
```

**输出:**

```go
225 222
-32767 32765
```

*   **浮点数:**在 Go 语言中，浮点数分为 ***两个*** 类别，如下表所示:

<figure class="table">

| 数据类型 | 

描述

 |
| --- | --- |
| **浮动 32** | 32 位 IEEE 754 浮点数 |
| **浮动 64** | 64 位 IEEE 754 浮点数 |

</figure>

**示例:**

## 去

```go
// Go program to illustrate
// the use of floating-point
// numbers
package main
import "fmt"

func main() {
    a := 20.45
    b := 34.89

    // Subtraction of two
    // floating-point number
    c := b-a

    // Display the result
    fmt.Printf("Result is: %f", c)

    // Display the type of c variable
    fmt.Printf("\nThe type of c is : %T", c) 
}
```

**输出:**

```go
Result is: 14.440000
The type of c is : float64
```

*   **复数:**复数分为两部分如下表所示。float32 和 float64 也是这些复数的一部分。内置函数从其虚部和实部创建一个复数，内置虚部和实部函数提取这些部分。

<figure class="table">

| 数据类型 | 

描述

 |
| --- | --- |
| **complex64** | 包含浮点数 32 作为实部和虚部的复数。 |
| **complex128** | 包含浮点数 64 作为实部和虚部的复数。 |

</figure>

**示例:**

## 去

```go
// Go program to illustrate
// the use of complex numbers
package main
import "fmt"

func main() {

   var a complex128 = complex(6, 2)
   var b complex64 = complex(9, 2)
   fmt.Println(a)
   fmt.Println(b)

   // Display the type
  fmt.Printf("The type of a is %T and "+
            "the type of b is %T", a, b)
}
```

**输出:**

```go
(6+2i)
(9+2i)
The type of a is complex128 and the type of b is complex64
```

#### 布尔运算

布尔数据类型只表示一位信息，要么是真，要么是假。布尔类型的值不会隐式或显式转换为任何其他类型。

**示例:**

## 去

```go
// Go program to illustrate
// the use of booleans
package main
import "fmt"

func main() {

    // variables
   str1 := "GeeksforGeeks"
   str2:= "geeksForgeeks"
   str3:= "GeeksforGeeks"
   result1:= str1 == str2
   result2:= str1 == str3

   // Display the result
   fmt.Println( result1)
   fmt.Println( result2)

   // Display the type of
   // result1 and result2
   fmt.Printf("The type of result1 is %T and "+
                   "the type of result2 is %T",
                             result1, result2)

}
```

**输出:**

```go
false
true
The type of result1 is bool and the type of result2 is bool
```

#### 用线串

字符串数据类型表示一系列 Unicode 代码点。或者换句话说，我们可以说一个字符串是一系列不可变的字节，这意味着一旦一个字符串被创建，你就不能改变这个字符串。字符串可能包含任意数据，包括人类可读形式的零值字节。

**示例:**

## 去

```go
// Go program to illustrate
// the use of strings
package main
import "fmt"

func main() {

    // str variable which stores strings
   str := "GeeksforGeeks"

   // Display the length of the string
   fmt.Printf("Length of the string is:%d",
                                  len(str))

   // Display the string
   fmt.Printf("\nString is: %s", str)

   // Display the type of str variable
   fmt.Printf("\nType of str is: %T", str)
}
```

**输出:**

```go
Length of the string is:13
String is: GeeksforGeeks
Type of str is: string
```