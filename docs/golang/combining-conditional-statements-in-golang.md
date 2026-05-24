# 组合 Golang 中的条件语句

> 原文:[https://www . geesforgeks . org/combining-conditional-statements-in-golang/](https://www.geeksforgeeks.org/combining-conditional-statements-in-golang/)

Go 是由罗伯特·格里森、罗布·派克和肯·汤普森在谷歌开发的开源编程语言。Go 在语法上类似于 C，但具有 CSP 风格的并发性和其他健壮编程语言的许多特性。常被裁判为 Golang 是因为域名，这种语言也有 [If/else](https://www.geeksforgeeks.org/go-decision-making-if-if-else-nested-if-if-else-if/) 条件。通常 If/else/else if 条件在用一个条件编写时会使程序变长并增加复杂性，因此我们可以组合两个条件。这些条件可以通过以下方式组合:-

**使用& &(与)运算符**

And (&&)是一种组合条件语句的方式，具有以下语法:

```go
if (condition1) && (condition2) {
......
}

```

这里，**条件 1** 代表第一个条件，**条件 2** 代表第二个条件。 ***& &*** 语句将条件结合起来，并以如下方式给出结果:

1.  如果条件 1 为*真*，条件 2 也为*真*，则结果为*真*。
2.  如果条件 1 为*真*，条件 2 为*假*，则结果为*假*。
3.  如果条件 1 为*假*，条件 2 为*真*，则结果为*假*。
4.  如果条件 1 为*假*，条件 2 也为*假*，则结果为*假*。

## 去

```go
package main

import "fmt"

// AND Condition
func main() {
    time := 18
    if time > 10 && time < 18 {
        fmt.Println("Time for work")
    }
}
```

**使用或运算符**

组合条件语句的“或”方式具有以下语法:

```go
if (condition1) || (condition2) {
.......
}

```

这里，**条件 1** 代表第一个条件，**条件 2** 代表第二个条件。 **||** 语句将条件结合起来，并以下列方式给出结果:

1.  如果条件 1 为*真*，条件 2 也为*真*，则结果为*真*。
2.  如果条件 1 为*真*，条件 2 为*假*，则结果为真 *e* 。
3.  如果条件 1 为*假*，条件 2 为*真*，则结果为真 *e* 。
4.  如果条件 1 为*假*，条件 2 也为*假*，则结果为*假*。

## 去

```go
package main

import "fmt"

// OR Condition
func main() {
    time := 14
    if time > 10 || time < 12 {
        fmt.Println("Hello geeks")
    }
}
```