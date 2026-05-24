# 检查戈朗的结构是否为空

> 原文:[https://www . geesforgeks . org/checking-structure-is-empty-or-not-in-golang/](https://www.geeksforgeeks.org/checking-if-structure-is-empty-or-not-in-golang/)

如果[结构](https://www.geeksforgeeks.org/structures-in-golang/)为空，意味着该特定结构内部不存在磁场。在 Golang，空结构的大小为零。每当用户想知道创建的结构是否为空时，他可以通过变量访问主函数中的结构。如果结构中不存在任何字段，他可以简单地显示结构为空。

**语法:**

```go
type structure_name struct {
    }

```

有不同的方法可以确定一个结构是否为空，如下所示。

**1)检查结构是否为空:**

```go
package main

import (
    "fmt"
)

type Book struct {
}

func main() {
    var bk Book
    if (Book{} == bk) {
        fmt.Println("It is an empty structure.")
    } else {
        fmt.Println("It is not an empty structure.")
    }
}
```

*输出:*

```go
It is an empty structure.
```

*说明:*在上面的例子中，我们创建了一个名为“Book”的结构，其中不存在字段。在主函数中，我们创建了一个变量来访问我们的结构。由于结构中没有指定字段，它将打印出它是一个空结构。现在，如果结构中存在字段，它将返回消息，说明它不是空结构，如下所示:

```go
package main

import (
    "fmt"
)

type Book struct {
    qty int
}

func main() {
    var bk Book
    if (Book{500} == bk) {
        fmt.Println("It is an empty structure.")
    } else {
        fmt.Println("It is not an empty structure.")
    }
}
```

*输出:*

```go
It is not an empty structure.
```

*说明:*在上面的例子中，我们创建了一个名为“Book”的结构，其中我们声明了一个名为“qty”的数据类型为 int 的字段。在主函数中，我们创建了一个变量来访问我们的结构。由于结构中存在一个字段，它将打印出它不是一个空结构。

**2)使用开关情况:**

```go
package main

import (
    "fmt"
)

type articles struct {
}

func main() {
    x := articles{}

    switch {
    case x == articles{}:
        fmt.Println("Structure is empty.")
    default:
        fmt.Println("Structure is not empty.")
    }
}
```

*输出:*

```go
Structure is empty.
```

*解释:*在这个例子中，我们创建了一个名为“articles”的结构，其中没有声明字段。在主函数内部，我们创建了一个变量“x”，并使用一个开关盒来访问我们的结构。由于结构中没有字段，程序将显示结构为空。