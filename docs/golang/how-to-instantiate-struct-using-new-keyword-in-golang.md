# 如何在 Golang 中使用 new 关键字实例化 Struct？

> 原文:[https://www . geesforgeks . org/how-instance-struct-using-new-keyword-in-golang/](https://www.geeksforgeeks.org/how-to-instantiate-struct-using-new-keyword-in-golang/)

一个[结构](https://www.geeksforgeeks.org/structures-in-golang/)主要是所有其他数据类型的一个持有者。通过使用指向结构的指针，我们可以轻松地操作/访问分配给结构的数据。我们可以使用新的关键字实例化 Struct，也可以在 Golang 中使用[指针地址运算符](https://www.geeksforgeeks.org/how-to-instantiate-struct-pointer-address-operator-in-golang/)，如下例所示:

**示例:**在这里，您可以看到我们正在使用 new 关键字实例化一个 Struct。

```go
// Golang program to show how to instantiate
// Struct using the new keyword
package main

import "fmt"

type emp struct {
    name   string
    empid  int
    salary int
}

func main() {

    // emp1 is a pointer to
    // an instance of emp
    // using new keyword
    emp1 := new(emp)
    emp1.name = "XYZ"
    emp1.empid = 1555
    emp1.salary = 25000
    fmt.Println(emp1)

    // emp2 is an instance of emp
    var emp2 = new(emp)
    emp2.name = "ABC"
    emp2.salary = 35000
    fmt.Println(emp2)
}
```

**输出:**

```go
&{XYZ 1555 25000}
&{ABC 0 35000}

```