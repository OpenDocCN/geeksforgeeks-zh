# Go 语言接口

> 原文: [https://www.geeksforgeeks.org/interfaces-in-golang/](https://www.geeksforgeeks.org/interfaces-in-golang/)

Go 语言接口不同于其他语言。在 Go 语言中，接口是一种自定义类型，用于指定一组一个或多个方法签名，并且接口是抽象的，因此不允许您创建接口的实例。但是您可以创建一个接口类型的变量，并且可以为这个变量分配一个具体的类型值，该值具有接口所需的方法。或者换句话说，接口是方法的集合，也是自定义类型。

## 如何创建接口？

在 Go 语言中，您可以使用以下语法创建接口:

```go
type interface_name interface {

    // Method signatures

}
```

**例如:**

```go
// Creating an interface
type myinterface interface {

    // Methods
    fun1() int
    fun2() float64
}
```

这里，接口名称包含在 `type` 和 `interface` 关键字之间，方法签名包含在大括号之间。

## 如何实现接口？

在 Go 语言中，需要实现接口中声明的所有方法来实现接口。Go 语言接口是隐式实现的。它不像其他语言那样包含任何特定的关键字来实现接口。如下例所示:

![](img/d88033f62eba553a77156430c022a9e0.png)

**示例:**

```go
// Golang program illustrates how
// to implement an interface
package main

import "fmt"

// Creating an interface
type tank interface {

    // Methods
    Tarea() float64
    Volume() float64
}

type myvalue struct {
    radius float64
    height float64
}

// Implementing methods of
// the tank interface
func (m myvalue) Tarea() float64 {

    return 2*m.radius*m.height +
        2*3.14*m.radius*m.radius
}

func (m myvalue) Volume() float64 {

    return 3.14 * m.radius * m.radius * m.height
}

// Main Method
func main() {

    // Accessing elements of
    // the tank interface
    var t tank
    t = myvalue{10, 14}
    fmt.Println("Area of tank :", t.Tarea())
    fmt.Println("Volume of tank:", t.Volume())
}
```

**输出:**

```go
Area of tank : 908
Volume of tank: 4396
```

## 要点

*   接口的零值为零。
*   当一个接口包含零个方法时，这种类型的接口称为空接口。因此，所有类型都实现了空接口。

**语法:**

```go
interface{}
```

*   **接口类型:** 接口有两种类型，一种是静态类型，另一种是动态类型。静态类型是接口本身，例如下面例子中的 `tank`。但接口没有静态值，所以它总是指向动态值。
    接口类型的变量包含实现了该接口的类型的值，因此该类型的值称为动态值，其类型称为动态类型。它也被称为具体值和具体类型。

**示例:**

```go
// Go program to illustrate the concept
// of dynamic values and types
package main

import "fmt"

// Creating an interface
type tank interface {

    // Methods
    Tarea() float64
    Volume() float64
}

func main() {

    var t tank
    fmt.Println("Value of the tank interface is: ", t)
    fmt.Printf("Type of the tank interface is: %T ", t)
}
```

**输出:**

```go
Value of the tank interface is:  <nil>
Type of the tank interface is: <nil>
```

在上面的例子中，我们有一个名为 `tank` 的接口。在本例中，`fmt.Println("Value of the tank interface is: ", t)` 语句返回接口的动态值，`fmt.Printf("Type of the tank interface is: %T", t)` 语句返回动态类型，即 `nil`，因为这里接口不知道谁在实现它。

*   **类型断言:** 在 Go 语言中，类型断言是应用于接口值的操作。或者换句话说，类型断言是提取接口值的过程。

**语法:**

```go
a.(T)
```

这里，`a` 是接口的值或表达式，`T` 是类型，也称为断言类型。类型断言用于检查其操作数的动态类型是否与断言的类型匹配。如果 `T` 是具体类型，那么类型断言检查给定的 `a` 的动态类型是否等于 `T`，这里如果检查成功，那么类型断言返回 `a` 的动态值。或者如果检查失败，那么操作将会死机。如果 `T` 是接口类型，那么类型断言检查给定的 `a` 的动态类型是否满足 `T`，这里，如果检查成功进行，则不提取动态值。

**示例:**

```go
// Go program to illustrate
// the type assertion
package main

import "fmt"

func myfun(a interface{}) {

    // Extracting the value of a
    val := a.(string)
    fmt.Println("Value: ", val)
}

func main() {

    var val interface{} = "GeeksforGeeks"

    myfun(val)
}
```

**输出:**

```go
Value:  GeeksforGeeks
```

在上例中，如果我们将这个 `val := a.(string)` 语句改为 `val := a.(int)`，那么程序就会死机。为了克服这个问题，我们使用以下语法:

```go
value, ok := a.(T)
```

这里如果 `a` 的类型等于 `T`，那么 `value` 包含 `a` 的动态值，`ok` 将设置为 `true`。如果 `a` 的类型不等于 `T`，那么 `ok` 设置为 `false`，`value` 包含零值，程序不会死机。如下图所示的程序:

**示例:**

```go
// Go program to illustrate type assertion
package main

import "fmt"

func myfun(a interface{}) {
    value, ok := a.(float64)
    fmt.Println(value, ok)
}

func main() {

    var a1 interface{} = 98.09

    myfun(a1)

    var a2 interface{} = "GeeksforGeeks"

    myfun(a2)
}
```

**输出:**

```go
98.09 true
0 false
```

*   **类型开关:** 在 Go 接口中，类型开关用于将接口的具体类型与 `case` 语句中提供的多种类型进行比较。它与类型断言类似，只有一个区别，即 `case` 指定的是类型，而不是值。您也可以将类型与接口类型进行比较。如下例所示:

**示例:**

```go
// Go program to illustrate type switch
package main

import "fmt"

func myfun(a interface{}) {

    // Using type switch
    switch a.(type) {

    case int:
        fmt.Println("Type: int, Value:", a.(int))
    case string:
        fmt.Println("\nType: string, Value: ", a.(string))
    case float64:
        fmt.Println("\nType: float64, Value: ", a.(float64))
    default:
        fmt.Println("\nType not found")
    }
}

// Main method
func main() {

    myfun("GeeksforGeeks")
    myfun(67.9)
    myfun(true)
}
```

**输出:**

```go
Type: string, Value:  GeeksforGeeks

Type: float64, Value:  67.9

Type not found
```

*   **接口的使用:** 在方法或函数中想要传递不同类型的参数时，可以使用接口，就像 `Println()` 函数一样。或者，当多个类型实现相同的接口时，也可以使用接口。