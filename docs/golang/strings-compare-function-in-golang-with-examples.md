# Golang 中的 string s.Compare()函数和示例

> Original: [https://www.geeksforgeeks.org/strings-compare-function-in-golang-with-examples/](https://www.geeksforgeeks.org/strings-compare-function-in-golang-with-examples/)

**Compare()函数**是 Golang 编程语言中的内置函数，用于比较两个字符串。 它用于按词典顺序(单词按字母顺序排列的顺序，类似于我们在字典中搜索单词的方式)比较两个字符串，或确定字符串是否相等。 它返回一个整数值，如下所示：

**语法：**

```go
func Compare(s1, s2 string) int
```

*   如果字符串相等，则返回 0(S1==S2)
*   如果字符串 1 大于字符串 2，则返回 1(S1>S2)
*   如果字符串 1 小于字符串 2，则返回-1(S1

**示例 1：**

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

发帖主题：Re：Колибри0.7.0

```go
-1
1
0

```

**解释：**第一个输出是-1，因为第一个字符串是“Geek”，它的字典顺序小于第二个字符串“GeeksforGeek”。 第二个输出为 1，因为第一个字符串是“GeeksforGeek”，它在字典顺序上大于第二个字符串“Geek”。 第三个输出为 0，因为第一个字符串是“Geek”，这等于第二个字符串“Geek”。

**示例 2：**

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

发帖主题：Re：Колибри0.7.0

```go
1
-1
-1

```

**解释：**第一个输出是 1，因为第一个字符串是“Apple”，它在字典顺序上大于第二个字符串“Apple”，因为使用 Unicode 字符集从左到右顺序比较字符，‘a’的 ASCII 值是 97，‘A’的 ASCII 值是 65。 因此，苹果比苹果更伟大。
第二个输出是-1，因为第一个字符串是“Apple”，它在字典顺序上比第二个字符串“Apricot”小。 第三个输出为-1，因为第一个字符串是“Apricot”，它在字典顺序上小于第二个字符串“Apple”，因为‘A’小于‘a’。