# Scala Stack :+()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-method-with-example-3/](https://www.geeksforgeeks.org/scala-stack-method-with-example-3/)

在 Scala 中，Scala . collection . mutatable 实现了堆栈数据结构。使用:+方法创建一个附加了元素的堆栈副本。

> **方法定义–**定义:+(元素:A)
> 
> **返回–**一个新的堆栈，该堆栈由该堆栈的所有元素组成，后跟 elem。

**示例#1:**

```scala
// Scala program of mutable stack :+() method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack 
        val q2 = List(11, 12, 13, 14, 15) 

        // Applying :+() method 
        val result = q2 :+ 100

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
List(11, 12, 13, 14, 15, 100)

```

**例 2:**

```scala
// Scala program of mutable stack /:() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val st1 = Stack(1, 2, 3)
        val st2 = Stack("Geeks", "For")

        // Applying :+() method 
        val result1 = st2 :+ st1

        // Display output 
        print(result1)

    } 
} 
```

**Output:**

```scala
Stack(Geeks, For, Stack(1, 2, 3))

```