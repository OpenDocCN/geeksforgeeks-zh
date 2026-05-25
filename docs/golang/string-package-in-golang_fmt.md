# Golang中的字符串包

> Original: [https://www.geeksforgeeks.org/string-package-in-golang/](https://www.geeksforgeeks.org/string-package-in-golang/)

Go Language 提供了一个字符串包，该包包含不同类型的函数来操作 UTF-8 编码的字符串。要访问字符串包的函数，需要在程序中借助 `import` 关键字导入字符串包。

## 函数列表

| 函数 | 描述 |
| --- | --- |
| `Compare` | 此函数返回一个整数，按字典顺序比较两个字符串。 |
| `Contains` | 此函数用于检查 `substr` 是否在 `s` 内。 |
| `ContainsAny` | 此函数用于检查 `s` 中是否存在字符中的任何 Unicode 码点。 |
| `ContainsRune` | 此函数用于检查 Unicode 码点 `r` 是否在 `s` 内。 |
| `Count` | 此函数用于计算给定字符串 `s` 中 `substr` 的非重叠实例的数量。 |
| `EqualFold` | 此函数用于检查 `s` 和 `t`（解释为 UTF-8 字符串）在 Unicode 大小写上是否相等。 |
| `Fields` | 此函数用于在 `unicode.IsSpace` 定义的一个或多个连续空格字符的每个实例周围分割给定的字符串 `s`，并返回子字符串切片；如果 `s` 仅包含空格，则返回空切片。 |
| `FieldsFunc` | 此函数用于分割字符串 `s`，并在每次运行满足 `f(c)` 的 Unicode 码点 `c` 时返回 `s` 的切片数组。 |
| `HasPrefix` | 此函数用于检查字符串 `s` 是否以 `prefix` 开头。 |
| `HasSuffix` | 此函数用于检查字符串 `s` 是否以 `suffix` 结尾。 |
| `Index` | 此函数返回 `substr` 在 `s` 中第一个实例的索引，如果 `substr` 不存在于 `s` 中，则返回 -1。 |
| `IndexAny` | 此函数返回 `s` 中第一个来自字符集 `chars` 的 Unicode 码点实例的索引，如果 `s` 中没有该字符集的 Unicode 码点，则返回 -1。 |
| `IndexByte` | 此函数返回 `c` 在 `s` 中第一个实例的索引，如果 `c` 不存在于 `s` 中，则返回 -1。 |
| `IndexFunc` | 此函数用于返回 `s` 中第一个满足 `f(c)` 的 Unicode 码点的索引，如果不满足 `f(c)`，则返回 -1。 |
| `IndexRune` | 此函数返回 Unicode 码点 `r` 在 `s` 中第一个实例的索引，如果 `rune` 不存在于 `s` 中，则返回 -1。 |
| `Join` | 此函数用于连接其第一个参数的元素。 |
| `LastIndex` | 此函数返回 `substr` 在 `s` 中最后一个实例的索引，如果 `substr` 不存在于 `s` 中，则返回 -1。 |
| `LastIndexAny` | 此函数返回 `s` 中最后一个来自字符集 `chars` 的 Unicode 码点实例的索引，如果 `s` 中没有该字符集的 Unicode 码点，则返回 -1。 |
| `LastIndexByte` | 此函数返回 `c` 在 `s` 中最后一个实例的索引，如果 `c` 不存在于 `s` 中，则返回 -1。 |
| `LastIndexFunc` | 此函数用于返回 `s` 中最后一个满足 `f(c)` 的 Unicode 码点的索引，如果不满足 `f(c)`，则返回 -1。 |
| `Map` | 此函数返回字符串 `s` 的副本，并根据映射函数修改其所有字符。 |
| `Repeat` | 此函数返回一个新字符串，由字符串 `s` 的计数副本组成。 |
| `Replace` | 此函数返回字符串 `s` 的副本，其中前 `n` 个不重叠的 `old` 实例被 `new` 替换。 |
| `ReplaceAll` | 此函数返回字符串 `s` 的副本，其中所有不重叠的 `old` 实例都被 `new` 实例替换。 |
| `Split` | 此函数用于在 `sep` 的每个实例周围分割所有子字符串 `s`。 |

## 类型

### Builder

| 方法 | 说明 |
| --- | --- |
| `(*Builder).Cap` | 此方法用于返回生成器的底层字节片的容量。 |
| `(*Builder).Grow` | 此方法用于在必要时增加 `b` 的容量，以保证另外 `n` 个字节的空间。 |
| `(*Builder).Len` | 此方法用于返回累积的字节数。 |
| `(*Builder).Reset` | 此方法用于将 `Builder` 重置为空。 |
| `(*Builder).String` | 此方法用于返回累积的字符串。 |
| `(*Builder).Write` | 此方法用于将 `p` 的内容附加到 `b` 的缓冲区。 |
| `(*Builder).WriteByte` | 此方法用于将字节 `c` 附加到 `b` 的缓冲区。 |
| `(*Builder).WriteRune` | 此方法用于将 Unicode 码点 `r` 的 UTF-8 编码附加到 `b` 的缓冲区。 |
| `(*Builder).WriteString` | 此方法用于将字符串的内容附加到 `b` 的缓冲区。它返回字符串的长度和零错误。 |

### Reader

| 方法 | 说明 |
| --- | --- |
| `NewReader` | 此函数用于从 `s` 返回新的读取器 `Reader`。 |
| `(*Reader).Len` | 此方法用于返回字符串未读部分的字节数。 |
| `(*Reader).Reset` | 此方法用于将读取器重置为从 `s` 读取。 |
| `(*Reader).Seek` | 此方法用于实现 `io.Seeker` 接口。 |
| `(*Reader).Size` | 此方法用于返回基础字符串的原始长度。 |
| `(*Reader).WriteTo` | 此方法用于实现 `io.WriterTo` 接口。 |

### Replacer

| 方法 | 说明 |
| --- | --- |
| `NewReplacer` | 此函数用于从旧的、新的字符串对列表中返回新的 `Replacer`。 |
| `(*Replacer).Replace` | 此方法用于返回执行了所有替换的 `s` 的副本。 |
| `(*Replacer).WriteString` | 此方法用于在执行所有替换的情况下将 `s` 写入 `w`。 |

## 示例

### 示例 1：`strings.Compare()`

```go
// Golang program to illustrate the use of
// the strings.Compare() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    var r1 = "Geeks"
    var r2 = "GeeksforGeeks"
    var r3 = "Geeks"

    // using the function
    fmt.Println(strings.Compare(r1, r2))
    fmt.Println(strings.Compare(r2, r3))
    fmt.Println(strings.Compare(r3, r1))

}
```

### 示例 2：`strings.IndexAny()`

```go
// Golang program to illustrate
// the strings.IndexAny() Function
package main

import (
    "fmt"
    "strings"
)

// Main function
func main() {

    // using the function
    fmt.Println(strings.IndexAny("Hey GFG?", "y"))

}
```