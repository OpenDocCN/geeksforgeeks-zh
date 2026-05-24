# Go 语言中的标识符

> 原文:[https://www.geeksforgeeks.org/identifiers-in-go-language/](https://www.geeksforgeeks.org/identifiers-in-go-language/)

在编程语言中，标识符用于识别目的。或者换句话说，标识符是程序组件的用户定义名称。在 Go 语言中，标识符可以是变量名、函数名、常量、语句标签、包名或类型。

**例:**

```go
package main
import "fmt"

func main() {

 var name = "GeeksforGeeks"

}

```

在上例中，共有三个标识符可用:

*   **Master:** Name of the package.
*   **Main:** The name of the function.
*   **Name:** The name of the variable

**定义标识符的规则:**定义有效 Go 标识符有一定的有效规则。这些规则应该被遵守，否则，我们会得到一个编译时错误。

*   The name of the identifier must begin with a letter or an underscore (_). And the name may contain letters "a-z" or "A-Z" or numbers 0-9 and the character "_".
*   The name of the identifier cannot start with a number.
*   The name of the identifier is case sensitive.
*   Keyword is not allowed as identifier name.
*   The length of the identifier is not limited, but it is recommended to use only the optimal length of 4–15 letters.

**例:**

```go
// Valid identifiers:
_geeks23
geeks
gek23sd
Geeks
geeKs
geeks_geeks

// Invalid identifiers:
212geeks
if
default

```

**注意:**

*   In Go language, there are some pre-declared identifiers that can be used for constants, types and functions. These names are not reserved; you can use them in the declaration. The following is a list of pre-declared identifiers:

    ```go
    For Constants:
    true, false, iota, nil

    For Types:
    int, int8, int16, int32, int64, uint,
    uint8, uint16, uint32, uint64, uintptr,
    float32, float64, complex128, complex64,
    bool, byte, rune, string, error

    For Functions:
    make, len, cap, new, append, copy, close, 
    delete, complex, real, imag, panic, recover

    ```

*   The identifier represented by the underscore character (_) is called a blank identifier. It is used as an anonymous placeholder, not a regular identifier, and has a special meaning in declaration, operand and assignment.
*   An identifier that is allowed to access it from another package is called a derived identifier. The exported identifiers are those that meet the following conditions:
    *   The first character of the exported identifier name should be Unicode capital letter.
    *   Identifiers should be declared in package blocks, either variable names or method names.
*   The uniqueness of the identifier means that it is unique with other sets of identifiers available in your program or package, and they will not be exported.