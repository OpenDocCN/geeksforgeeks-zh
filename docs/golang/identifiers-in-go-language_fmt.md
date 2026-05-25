# Go 语言中的标识符

> 原文: [https://www.geeksforgeeks.org/identifiers-in-go-language/](https://www.geeksforgeeks.org/identifiers-in-go-language/)

在编程语言中，标识符用于识别目的。或者换句话说，标识符是程序组件的用户定义名称。在 Go 语言中，标识符可以是变量名、函数名、常量、语句标签、包名或类型。

## 示例

```go
package main
import "fmt"

func main() {
    var name = "GeeksforGeeks"
}
```

在上例中，共有三个标识符可用：

*   `main`：包的名称。
*   `main`：函数的名称。
*   `name`：变量的名称。

## 定义标识符的规则

定义有效 Go 标识符有一定的有效规则。这些规则应该被遵守，否则，我们会得到一个编译时错误。

*   标识符的名称必须以字母或下划线 (`_`) 开头。名称可以包含字母 `"a-z"` 或 `"A-Z"` 或数字 `0-9` 以及字符 `"_"`。
*   标识符的名称不能以数字开头。
*   标识符的名称区分大小写。
*   关键字不允许作为标识符名称。
*   标识符的长度没有限制，但建议只使用 4-15 个字母的最佳长度。

## 有效和无效标识符示例

```go
// 有效标识符:
_geeks23
geeks
gek23sd
Geeks
geeKs
geeks_geeks

// 无效标识符:
212geeks
if
default
```

## 注意

*   在 Go 语言中，有一些预声明的标识符可用于常量、类型和函数。这些名称不是保留的；你可以在声明中使用它们。以下是预声明标识符的列表：

```go
// 常量:
true, false, iota, nil

// 类型:
int, int8, int16, int32, int64, uint,
uint8, uint16, uint32, uint64, uintptr,
float32, float64, complex128, complex64,
bool, byte, rune, string, error

// 函数:
make, len, cap, new, append, copy, close,
delete, complex, real, imag, panic, recover
```

*   由下划线字符 (`_`) 表示的标识符称为空白标识符。它用作匿名占位符，而不是常规标识符，并在声明、操作数和赋值中具有特殊含义。
*   允许从另一个包访问的标识符称为导出标识符。导出的标识符是满足以下条件的标识符：
    *   导出标识符名称的第一个字符应该是 Unicode 大写字母。
    *   标识符应在包块中声明，无论是变量名还是方法名。
*   标识符的唯一性意味着它在你的程序或包中与其他可用的标识符集合是唯一的，并且它们不会被导出。