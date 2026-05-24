# 【Scala 和 Golang 的区别

> 原文:[https://www . geesforgeks . org/Scala 和-golang 之间的差异/](https://www.geeksforgeeks.org/differences-between-scala-and-golang/)

[Scala](https://www.geeksforgeeks.org/scala-programming-language/) 是一种通用、高级、多范式的编程语言。也支持函数式编程方法，这是一种纯面向对象的编程语言。Scala 程序可以转换成字节码，并且可以在 JVM (Java 虚拟机)上运行。Scala 代表可伸缩语言。它还提供了 Javascript 运行时。

**例:**

## 斯卡拉

```scala
// Scala program to print Hello GFG! 

// Creating object 
object Geeks { 

// Main method 
def main(args: Array[String]) 
{ 

    // prints Hello, GFG! 
    println("Hello, GFG!") 
} 
} 
```

**输出:**

```scala
Hello GFG!
```

[Golang](https://www.geeksforgeeks.org/golang/) 是一种过程化的静态类型编程语言，其语法类似于 [**C**](https://www.geeksforgeeks.org/c-programming-language/) 编程语言。有时被称为 **围棋编程语言** 。它于 2007 年由罗伯特·格里森、罗布·派克和肯·汤普森在谷歌开发，但于 2009 年作为开源编程语言推出，主要用于谷歌的生产系统。

**例:**

## 去

```scala
// Golang program
package main

import "fmt"

// Main function
func main() {

    fmt.Println("Hello Geeks")
}
```

**输出:**

```scala
Hello Geeks
```

### Golang 对 scala

<figure class="table">

| 

戈朗

 | 

斯卡拉

 |
| --- | --- |
| 对于大数据世界，它不是首选。 | 与 Python 一起成为大数据领域的首选。 |
| 文件扩展名为 ***。**去*。 | 文件扩展名为 ***。sc*** 或 ***。斯卡拉*** 。 |
| 就开发人员和语言工作而言，成本较低。 | 就开发人员和语言工作而言，成本很高。 |
| Go 没有 while 循环和 do while 语法。相反，Go 使用 for 循环来执行 while 循环。 | Scala 支持 while 循环和 do-while 循环。 |
| Go 不允许隐式类型转换。 | Scala 允许隐式类型转换。 |
| Golang 不是一种面向对象的编程语言，但是我们可以使用某些方法来实现它们。 | Scala 是一种面向对象的编程语言。 |
| Golang 适合云原生、无服务器功能和微服务。 | Scala 最适合单片和小型服务。 |
| 流处理的更好选择。 | 一般不喜欢进行流处理。 |
| Go 提供 Goroutine 功能，使 Goroutine 能够独立运行或与其他 Goroutine 一起运行。 | Scala 不支持 Goroutine 类型的功能。 |

</figure>