# 【Scala 和 Golang 的区别

> 原文:[https://www . geesforgeks . org/Scala 和-golang 之间的差异/](https://www.geeksforgeeks.org/differences-between-scala-and-golang/)

[Scala](https://www.geeksforgeeks.org/scala-programming-language/) 是一种通用、高级、多范式的编程语言。也支持函数式编程方法，这是一种纯面向对象的编程语言。Scala 程序可以转换成字节码，并且可以在 JVM (Java 虚拟机)上运行。Scala 代表可伸缩语言。它还提供了 Javascript 运行时。

**例:**

## 斯卡拉

```go
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

```go
Hello GFG!
```

[Golang](https://www.geeksforgeeks.org/golang/) 是一种过程化的静态类型编程语言，其语法类似于 [**C**](https://www.geeksforgeeks.org/c-programming-language/) 编程语言。有时被称为 **围棋编程语言** 。它于 2007 年由罗伯特·格里森、罗布·派克和肯·汤普森在谷歌开发，但于 2009 年作为开源编程语言推出，主要用于谷歌的生产系统。

**例:**

## 去

```go
// Golang program
package main

import "fmt"

// Main function
func main() {

    fmt.Println("Hello Geeks")
}
```

**输出:**

```go
Hello Geeks
```

### Golang 对 scala

<figure class="table">T3

|  | golang

Scala

 |
| --- | --- |
| For the big data world, it is not the first choice. | Together with Python, it has become the first choice in the field of big data. |
| The file name extension is ***. Go*** . | The file extension is ***. Sc*** or ***. Scala*** |
| Low cost in terms of developers and language work. | The cost is high in terms of developers and language work. |
| Go has no while loop and do while syntax. Instead, Go uses the for loop to execute the while loop. | Scala supports while loop and do-while loop. |
| Go does not allow implicit type conversion. | Scala allows implicit type conversion. |
| Golang is not an object-oriented programming language, but we can use certain methodology to implement them. | Scala is an object-oriented programming language. |
| Golang is suitable for cloud native, serverless functions, and microservices. | Scala is best for monolithic and mini services. |
| A better choice for flow processing. | Generally, I don't like stream processing. |
| Goroutine function is provided, which enables Goroutine to run independently or together with other Goroutines. | Scala does not support the Goroutine class function. |

</figure>