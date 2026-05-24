# Golang

中的串包

> Original: [https://www.geeksforgeeks.org/string-package-in-golang/](https://www.geeksforgeeks.org/string-package-in-golang/)

Go Language 提供了一个字符串包，该包包含不同类型的函数来操作 UTF-8 编码的字符串。 要访问字符串包的函数，需要在程序中借助 IMPORT 关键字导入字符串包。-

<figure class="table">

| Function | Description |
| --- | --- |
| **function comparison** | This function returns an integer that compares two strings in dictionary order. |
| The **function contains** | This function is used to check whether substr is within s. |
| **function container Any** | This function is used to check whether there are Unicode code points within s in the character. |
| **函数容器运行** | This function is used to check whether the Unicode code point r is within s. |
| **函数计数** | This function is used to calculate the number of non-overlapping instances of substr in a given string s. |
| **Func EqualFold** | This function is used to check whether s and t (interpreted as UTF-8 strings) are equal in Unicode case. |
| **功能字段** | This function is used to split the given string s around each instance of one or more consecutive space characters defined by unicode.IsSpace, and returns a substring slice or empty slice of s if s contains only spaces. |
| **函数字段函数** | This function is used to split the string s and return an array of slices of s each time you run Unicode code point c that satisfies f (C). |
| **函数 HasPrefix** | This function is used to check. |
| **HasSuffix** | This function is used to check whether the string s ends with a suffix. |
| **functional index** | This function returns the index of the first substr instance in s, or-1 if substr does not exist in s. |
| **函数索引任意** | This function returns the index of the first instance of any Unicode. Or if there is no Unicode code point from the character in s. |
| **函数索引字节** | This function returns the index of the first instance of c in s, or-1 if c does not exist in s. |
| **函数索引函数** | This function is used to return the index to s of the first Unicode code point that satisfies f (C), or-1 if it does not satisfy f (C). |
| **函数索引运行** | This function returns the index of the first instance of Unicode code point r, or-1 if rune does not exist in s. |
| **函数连接** | This function is used to concatenate the element of its first parameter. |
| **函数最后索引** | This function returns the index of the last instance of substr in s, or-1 if substr does not exist in s. |
| **Funcc LastIndexAny** | This function returns the index of the last instance. Returns if the Unicode code point for the character does not exist in s. |
| **函数最后索引字节** | This function returns the index of the last instance of c in s, or-1 if c does not exist in s. |
| **func LastIndexFunc** **function LastIndexFunc** **. If not, it is-1\.** |
| **函数映射** | This function returns a copy of the string s and modifies all its characters according to the mapping function. |
| **函数重复** | This function returns a new string consisting of a counted copy of the string s. |
| **功能替换** | This function returns a copy of the string s, where the first n non-overlapping old instances are replaced by new ones. |
| **Funcc ReplaceAll** | This function returns a copy of the string s, where all the old instances that do not overlap are replaced by the new instance. |
| **函数拆分** | This function is used to split all substrings |

</figure>

### 类型生成器

<figure class="table">

| 方法 / 条理 / 系统计划 / 类函数 | 说明 |
| --- | --- |
| **func(*Builder)Cap** | 此方法用于返回生成器的底层字节片的容量。 |
| **func(*Builder)Growth** | 此方法用于在必要时增加 b 的容量，以保证另外 n 个字节的空间。 |
| **func(*Builder)LEN** | 此方法用于返回累积的字节数。 |
| **func(*Builder)Reset** | 此方法用于将 Builder 重置为空。 |
| **func(*Builder)字符串** | 此方法用于返回累积的字符串。 |
| **func(*Builder)Write** | 此方法用于将 p 的内容附加到 b 的缓冲区。 |
| **func(*Builder)WriteByte** | 此方法用于将字节 c 附加到 b 的缓冲区。 |
| **func(*Builder)WriteRune** | 此方法用于将 Unicode 码点 r 的 UTF-8 编码附加到 b 的缓冲区。 |
| **func(*Builder)WriteString** | 此方法用于将字符串的内容附加到 b 的缓冲区。 它返回字符串的长度和零错误。 |

</figure>

### 类型阅读器

<figure class="table">

| 方法 / 条理 / 系统计划 / 类函数 | 说明 |
| --- | --- |
| **func newread** | 此函数用于从 s 返回新的读取器读数。 |
| **func(*Reader)LEN** | 此方法用于返回字符串未读部分的字节数。 |
| **func(*Reader)Reset** | 此方法用于将读取器重置为从 s 读取。 |
| **func(*Reader)Seek** | 此方法用于实现 io.Seeker 接口。 |
| **func(*Reader)size** | 此方法用于返回基础字符串的原始长度。 |
| **func(*Reader)WriteTo** | 此方法用于实现 io.WriterTo 接口。 |

</figure>

### 类型替换程序

<figure class="table">

| 方法 / 条理 / 系统计划 / 类函数 | 说明 |
| --- | --- |
| **func NewReplacer** | 此函数用于从旧的、新的字符串对列表中返回新的 Replacer。 |
| **func(*Replacer)Replace** | 此方法用于返回执行了所有替换的 s 的副本。 |
| **func(*Replacer)WriteString** | 此方法用于在执行所有替换的情况下将 s 写入 w。 |

</figure>

**示例 1：**和

## GO

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

发帖主题：Re：Колибри0.7.8.0

**示例 2：**

## 行走 / 离开 / 变成 / 走

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

发帖主题：Re：Колибри0.7.8.0