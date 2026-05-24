# 如何在 Golang 中给结构体类型增加一个方法？

> 原文:[https://www . geesforgeks . org/how-to-add-a-method-to-struct-type-in-golang/](https://www.geeksforgeeks.org/how-to-add-a-method-to-struct-type-in-golang/)

结构由数据组成，但除此之外，[结构](https://www.geeksforgeeks.org/structures-in-golang/)也以方法的形式讲述行为。[附在结构上的方法](https://www.geeksforgeeks.org/methods-in-golang/)非常类似于正规函数的定义，唯一的变化是你需要额外指定它的类型。

一个普通的函数返回一个整数并且不带任何参数，看起来像。

```go
func function_name() int {
    //code
}

```

将上述函数与 type_name()类型相关联看起来像。

```go
type type_name struct { }
func (m type_name) function_name() int {
    //code
}

```

在下面的代码中，一个 Area()函数被添加到一个结构 Rect 中。这里，Area()显式地与 Rect 类型配合使用 **func (re Rect) Area() int**

**示例:**

```go
package main

import "fmt"

// taking a struct
type Rect struct {
    len, wid int
}

func (re Rect) Area() int {
    return re.len * re.wid
}

func main() {
    r := Rect{10, 12}
    fmt.Println("Length and Width are:", r)
    fmt.Println("Area of Rectangle: ", r.Area())
}
```

**输出:**

```go
Length and Width are: {10, 12}
Area of Rectangle: 120

```

Go 语言不使用像**这样的关键字**或 **self** ，相反，在 Go 语言中，当您定义一个与类型相关联的方法时，它被赋予一个命名变量 **(r Rect)** (例如在上述情况下)，然后在该方法中使用 **re** 变量。

在上面的代码中，Rect 的实例作为值传递给**，以调用方法 Area()。也可以参考**通过**。无论您用来调用方法的实例是指针还是值，调用方法都没有区别，Go 会自动为您进行转换。**

 ```go
package main

import "fmt"

// taking a struct
type Rect struct {
    len, wid int
}

func (re Rect) Area_by_value() int {
    return re.len * re.wid
}

func (re *Rect) Area_by_reference() int {
    return re.len * re.wid
}

// main function
func main() {
    r := Rect{10, 12}
    fmt.Println("Length and Width is:", r)
    fmt.Println("Area of Rectangle is:", r.Area_by_value())
    fmt.Println("Area of Rectangle is:", r.Area_by_reference())
    fmt.Println("Area of Rectangle is:", (&r).Area_by_value())
    fmt.Println("Area of Rectangle is:", (&r).Area_by_reference())
}
```** 

**输出:**

```go
Length and Width is: {10, 12}
Area of Rectangle is: 120
Area of Rectangle is: 120
Area of Rectangle is: 120
Area of Rectangle is: 120

```

在上面的代码中，我们定义了两个类似的方法，一个以实例(Rect)为指针，另一个以值为指针。这两种方法都是通过一个值 r 和一个地址&r 来调用的。但是由于 Go 执行适当的转换，它会显示相同的结果。