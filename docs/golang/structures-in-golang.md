# Golang

中的结构

> Original: [https://www.geeksforgeeks.org/structures-in-golang/](https://www.geeksforgeeks.org/structures-in-golang/)

Golang 中的结构或结构是用户定义的类型，它允许将可能不同类型的项分组/组合成单个类型。 任何具有某些属性/字段集的真实实体都可以表示为结构。 这个概念通常与面向对象编程中的类进行比较。 它可以被称为不支持继承但支持组合的轻量级类。

例如，地址有名称、街道、城市、州和 PIN 码。 将这三个属性分组到单个结构*地址*中是有意义的，如下所示。

**声明结构：**

```go
 type Address struct {
      name string 
      street string
      city string
      state string
      Pincode int
}

```

在上面，***type***关键字引入了一个新类型。 后跟类型名称(*Address*)和关键字*struct*来说明我们正在定义一个结构。 该结构包含花括号内各种字段的列表。 每个字段都有名称和类型。

**注意：**我们还可以通过组合相同类型的各个字段来压缩它们，如下例所示：

```go
type Address struct {
    name, street, city, state string
    Pincode int
}

```

**定义结构：**声明结构的语法：

```go
var a Address

```

上面的代码创建了一个*类型的变量 ADDRESS*，该变量默认设置为零。 对于结构，零表示所有字段都设置为其对应的零值。 因此，字段 Name、Street、City、State 被设置为“”，Pincode 被设置为 0。

您还可以使用结构文字来*初始化结构类型的变量，如下所示：*

```go
var a = Address{"Akshay", "PremNagar", "Dehradun", "Uttarakhand", 252636}
```

**注：**

*   始终以在结构中声明字段值的相同顺序传递字段值。 此外，您不能只使用上面的语法初始化字段的子集。
*   Go also supports the *name: value* syntax for initializing a struct (the order of fields is irrelevant when using this syntax). And this allows you to initialize only a subset of fields. All the uninitialized fields are set to their corresponding zero value.

    *示例：*

    > Var a=地址{名称：“Akshay”，街道：“PremNagar”，州：“Uttarakhandd”，密码：252636}//城市：“”

```go
// Golang program to show how to
// declare and define the struct

package main

import "fmt"

// Defining a struct type
type Address struct {
    Name    string
    city    string
    Pincode int
}

func main() {

    // Declaring a variable of a `struct` type
    // All the struct fields are initialized 
    // with their zero value
    var a Address 
    fmt.Println(a)

    // Declaring and initializing a
    // struct using a struct literal
    a1 := Address{"Akshay", "Dehradun", 3623572}

    fmt.Println("Address1: ", a1)

    // Naming fields while 
    // initializing a struct
    a2 := Address{Name: "Anikaa", city: "Ballia",
                                 Pincode: 277001}

    fmt.Println("Address2: ", a2)

    // Uninitialized fields are set to
    // their corresponding zero-value
    a3 := Address{Name: "Delhi"}
    fmt.Println("Address3: ", a3)
}
```

发帖主题：Re：Колибри0.7.0

```go
{  0}
Address1:  {Akshay Dehradun 3623572}
Address2:  {Anikaa Ballia 277001}
Address3:  {Delhi  0}

```

### 如何访问结构的字段？

要访问*struct*的各个字段，必须使用点*(.)*运算符。

**示例：**

```go
// Golang program to show how to
// access the fields of struct
package main

import "fmt"

// defining the struct
type Car struct {
    Name, Model, Color string
    WeightInKg         float64
}

// Main Function
func main() {
    c := Car{Name: "Ferrari", Model: "GTC4",
            Color: "Red", WeightInKg: 1920}

    // Accessing struct fields
    // using the dot operator
    fmt.Println("Car Name: ", c.Name)
    fmt.Println("Car Color: ", c.Color)

    // Assigning a new value
    // to a struct field
    c.Color = "Black"

    // Displaying the result
    fmt.Println("Car: ", c)
}
```

发帖主题：Re：Колибри0.7.0

```go
Car Name:  Ferrari
Car Color:  Red
Car:  {Ferrari GTC4 Black 1920}

```

### 指向结构的指针

[GO 编程语言或 Golang 中的指针](https://www.geeksforgeeks.org/pointers-in-golang/)是用于存储另一个变量的内存地址的变量。 您还可以创建指向结构的指针，如下例所示：

```go
// Golang program to illustrate
// the pointer to struct
package main

import "fmt"

// defining a structure
type Employee struct {
    firstName, lastName string
    age, salary int
}

func main() {

    // passing the address of struct variable
    // emp8 is a pointer to the Employee struct
    emp8 := &Employee{"Sam", "Anderson", 55, 6000}

    // (*emp8).firstName is the syntax to access
    // the firstName field of the emp8 struct
    fmt.Println("First Name:", (*emp8).firstName)
    fmt.Println("Age:", (*emp8).age)
}
```

发帖主题：Re：Колибри0.7.0

```go
First Name: Sam
Age: 55

```

*Golang*为我们提供了使用*emp8.firstName*而不是显式取消引用*(*emp8).firstName*来访问*FirstName*字段的选项。 下面是说明这一点的示例：

```go
// Golang program to illustrate
// the pointer to struct
package main

import "fmt"

// Defining a structure
type Employee struct {
    firstName, lastName string
    age, salary         int
}

// Main Function
func main() {

    // taking pointer to struct
    emp8 := &Employee{"Sam", "Anderson", 55, 6000}

    // emp8.firstName is used to access
    // the field firstName
    fmt.Println("First Name: ", emp8.firstName)
    fmt.Println("Age: ", emp8.age)
}
```

发帖主题：Re：Колибри0.7.0

```go
First Name:  Sam
Age:  55

```