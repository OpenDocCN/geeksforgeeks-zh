# Golang 中的 main 和 init 函数

> Original: [https://www.geeksforgeeks.org/main-and-init-function-in-golang/](https://www.geeksforgeeks.org/main-and-init-function-in-golang/)

围棋语言保留了两个专用函数，分别是**main()**和**init()**函数。

#### Main()函数

在 GO 语言中，**Main**包是一个特殊的包，它与可执行程序一起使用，该包包含*Main()*函数。 *main()*函数是一种特殊类型的函数，它是可执行程序的入口点。 它不需要任何参数，也不返回任何内容。 GO 会自动调用*main()*函数，因此不需要显式调用*main()*函数，每个可执行程序必须包含单个主包和*main()*函数。

**示例：**

```go
// Go program to illustrate the
// concept of main() function

// Declaration of the main package
package main

// Importing packages
import (
    "fmt"
    "sort"
    "strings"
    "time"
)

// Main function
func main() {

    // Sorting the given slice
    s := []int{345, 78, 123, 10, 76, 2, 567, 5}
    sort.Ints(s)
    fmt.Println("Sorted slice: ", s)

    // Finding the index
    fmt.Println("Index value: ", strings.Index("GeeksforGeeks", "ks"))

    // Finding the time
    fmt.Println("Time: ", time.Now().Unix())

}
```

发帖主题：Re：Колибри0.7.0

```go
Sorted slice:  [2 5 10 76 78 123 345 567]
Index value:  3
Time:  1257894000

```

#### Init()函数

**init()**函数就像 main 函数一样，既不接受任何参数，也不返回任何内容。 此函数存在于每个包中，并且在初始化包时调用此函数。 该函数是隐式声明的，因此您不能从任何地方引用它，并且允许您在同一程序中创建多个**init()**函数，并且它们按照创建的顺序执行。 您可以在程序中的任何位置创建 init()函数，它们是按词法文件名顺序(字母顺序)调用的。 并且允许在 init()函数的情况下放入语句，但始终要记住 init()函数是在 main()函数调用之前执行的，因此它不依赖于**main()**函数。 函数**init()**的主要目的是初始化无法在全局上下文中初始化的全局变量。

**示例：**

```go
// Go program to illustrate the
// concept of init() function

// Declaration of the main package
package main

// Importing package
import "fmt"

// Multiple init() function
func init() {
    fmt.Println("Welcome to init() function")
}

func init() {
    fmt.Println("Hello! init() function")
}

// Main function
func main() {
    fmt.Println("Welcome to main() function")
}
```

发帖主题：Re：Колибри0.7.0

```go
Welcome to init() function
Hello! init() function
Welcome to main() function

```