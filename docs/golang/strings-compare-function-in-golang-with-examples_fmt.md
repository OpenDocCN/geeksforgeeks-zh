# Golang中的string.Compare()函数和示例

> Original: [https://www.geeksforgeeks.org/strings-compare-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-compare-function-in-golang-with-examples/)

`Compare()`函数是Golang编程语言中的内置函数，用于比较两个字符串。它用于按词典顺序（单词按字母顺序排列的顺序，类似于我们在字典中搜索单词的方式）比较两个字符串，或确定字符串是否相等。它返回一个整数值，如下所示：

## 语法

```go
func Compare(s1, s2 string) int
```

*   如果字符串相等，则返回`0`（`s1 == s2`）
*   如果字符串1大于字符串2，则返回`1`（`s1 > s2`）
*   如果字符串1小于字符串2，则返回`-1`（`s1 < s2`）

## 示例1

```go
// Golang program to illustrate the use of
// the strings.Compare() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    var s1 = "Geeks"
    var s2 = "GeeksforGeeks"
    var s3 = "Geeks"

    // using the function
    fmt.Println(strings.Compare(s1, s2))
    fmt.Println(strings.Compare(s2, s3))
    fmt.Println(strings.Compare(s3, s1))

}
```

**解释：**第一个输出是`-1`，因为第一个字符串是“Geeks”，它的字典顺序小于第二个字符串“GeeksforGeeks”。第二个输出为`1`，因为第一个字符串是“GeeksforGeeks”，它在字典顺序上大于第二个字符串“Geeks”。第三个输出为`0`，因为第一个字符串是“Geeks”，这等于第二个字符串“Geeks”。

## 示例2

```go
// Golang program to illustrate the use of
// the strings.Compare() Function
package main

import (
    "fmt"
    "strings"
)

func main() {

    var s1 = "apple"
    var s2 = "Apple"
    var s3 = "Apricot"

    // using the function
    fmt.Println(strings.Compare(s1, s2))
    fmt.Println(strings.Compare(s2, s3))
    fmt.Println(strings.Compare(s3, s1))

}
```

**解释：**第一个输出是`1`，因为第一个字符串是“apple”，它在字典顺序上大于第二个字符串“Apple”，因为使用Unicode字符集从左到右顺序比较字符，‘a’的ASCII值是97，‘A’的ASCII值是65。因此，“apple”比“Apple”更大。
第二个输出是`-1`，因为第一个字符串是“Apple”，它在字典顺序上比第二个字符串“Apricot”小。第三个输出为`-1`，因为第一个字符串是“Apricot”，它在字典顺序上小于第二个字符串“Apple”，因为‘A’小于‘a’。