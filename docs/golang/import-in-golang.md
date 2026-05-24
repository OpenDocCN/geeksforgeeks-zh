# 在戈朗进口

> 原文:[https://www.geeksforgeeks.org/import-in-golang/](https://www.geeksforgeeks.org/import-in-golang/)

**先决条件学习:** [在 Windows 上安装 Go](https://www.geeksforgeeks.org/how-to-install-go-on-windows/)/[在 MacOS 上安装 Go](https://www.geeksforgeeks.org/how-to-install-golang-on-macos/)

从技术上来说，一个**包**本质上是一个特定目的的源代码容器。这意味着包装是一个胶囊，里面装有多种药物/药物成分，将它们结合在一起，并在一个迷你外壳中保护它们。这种胶囊很容易携带到任何地方，可以随意使用，对吗？是的，没错。您可以在一个包中编写数千行代码、数百个函数、n 个操作以及更多内容，并将其存储起来，以便您可以在需要时随时将包抓取到主文件中。许多软件包都预装了 Go。

包是非常重要的，因为在从最基本的程序到高级复杂代码的所有程序中，都使用这些包。一个包可以确保没有重复的代码，并且主代码以一种结构良好的方式尽可能简洁。

**例:**

```go
package main

```

主包包含负责使当前程序可编译和可运行的代码。

### 导入关键词及其重要性

正如我们已经讨论过的，包是帮助我们在 Go 中编码的情侣。现在的问题是我们如何在程序中使用它们？答案很简单:使用“ **<u>导入</u>** ”关键词。顾名思义，这个关键字从 **$GOPATH** 的目录(如果没有提到路径)或者从提到的目录中导入指定的包。导入简单地说就是把指定的包从它的源位置带到目标代码，使主程序。在 Go 中导入非常重要，因为它有助于带来运行程序所必需的包。本文涵盖了“Go 中的导入”的各个方面。

**例:**

```go
import "fmt" --------------------------------> fmt is the name of a package
import "os" ---------------------------------> os is the name of a package
import "<u>github.com/gopherguides/greet</u>" ------> the underlined part is the path of the package

```

### 格朗进口商品类型

嗯，是的，有不同类型的导入，其中许多对许多用户来说是未知的。让我们详细讨论这些类型。让我们考虑一个包:假设**数学**并观察导入风格的差异。

### 1.直接进口

Go 通过遵循简单的语法支持包的直接导入。可以使用 import 关键字逐个导入单个和多个包。

**例:**

```go
Single:
import "fmt"

Multiple one-by-one:
import "fmt"
import "math"

```

## Go

```go
// Golang program to demonstrate the 
// application of direct import
package main

import "fmt"

// Main function
func main() {
    fmt.Println("Hello Geeks")
}
```

### 2.分组导入

Go 还支持分组导入。这意味着您不必多次编写 import 关键字；相反，您可以使用关键字 import 后跟圆括号，()，并在圆括号中提到您想要导入的所有包。这也是一个直接导入，但不同的是，您在这里提到了一个导入中的多个包()。查看示例，了解分组导入命令的语法。

**示例:**

```go
import(
    "fmt"
    "math"
)

```

## 去

```go
// A program to demonstrate the
// application of grouped import
package main

import (
    "fmt"
    "math"
)

// Main function
func main() {

    // math.Exp2(5) returns 
    // the value of 2^5, wiz 32
    c := math.Exp2(5)

    // Println is a function in fmt package 
    // which prints value of c in a new
    // line on console
    fmt.Println(c)

}
```

### 3.嵌套导入

Go 也支持嵌套导入。就像我们听说嵌套导入这个名字一样，我们突然想到嵌套循环的梯形 if-else 语句等。但是嵌套导入不是那种类型的:它不同于那些嵌套元素。这里的嵌套导入是指从一个更大的包文件中导入一个子包。例如，有时您只需要使用整个包中的一个特定函数，因此您不想导入整个包并增加代码的内存大小，简而言之，您只需要一个子包。在这种情况下，我们使用嵌套导入。为了更好地理解，请看下面的语法和示例代码。

**例:**

```go
import "math/rand"

```

## Go

```go
// Golang Program to demonstrate
// application of nested import
package main

 import (
    "fmt"
    "math/rand"
)

func main() {

    // this generates & displays a
    // random integer value < 100
    fmt.Println(rand.Int(100))
}
```

### 4.别名导入

它也支持别名导入。嗯，有时我们只是厌倦了在代码中一遍又一遍地写全名，因为它可能很长或很无聊，所以你希望给它重新命名。别名导入就是这样。它不会重命名包，但会使用您为包提到的名称，并创建该包的别名，给人一种包名称已被重命名的印象。考虑语法示例和示例代码，以便更好地理解别名导入。

**例:**

```go
import m "math"
import f "fmt"

```

## Go

```go
// Golang Program to demonstrate
// the application of aliased import
package main

import (
    f "fmt"
    m "math"
)

// Main function
func main() {

    // this assigns value 
    // of 2^5 = 32 to var c
    c := m.Exp2(5)    

    // this prints the 
    // value stored in var c
    f.Println(c)                
}
```

### 5.点导入

Go 支持 dot 导入。Dot import 是大多数用户没有听说过的东西。这基本上是一种罕见的进口类型，主要用于测试目的。测试人员使用这种导入来测试他们的公共结构/功能/包元素是否正常运行。Dot import 提供了使用包元素的额外好处，无需提及包的名称，并且可以直接使用。尽管它提供了许多额外的好处，但它也带来了一些缺点，例如名称空间冲突。为了更好地理解点导入，请参考语法示例和示例代码。

**例:**

```go
import . "math"

```

## Go

```go
// Golang Program to demonstrate 
// the application of dot import
package main

import (
    "fmt"
    . "math"
)

func main() {

    // this prints the value of
    // 2^5 = 32 on the console
    fmt.Println(Exp2(5))      
}
```