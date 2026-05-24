# Scala Stack +:()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-method-with-example-4/](https://www.geeksforgeeks.org/scala-stack-method-with-example-4/)

在 Scala 中，Scala . collection . mutatable 实现了堆栈数据结构。+:方法类似于堆栈中的++方法，它给出了一个堆栈的副本，并在前面添加了一个元素。请注意，结束运算符是右关联的。

> **方法定义–**def+:(elem:A)
> 
> **返回–**一个新的堆栈，由 elem 和该堆栈的所有元素组成。

**示例#1:**

```scala
// Scala program of mutable stack +:() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a value 
        val q1 = 1

        val q2 = Stack("for", "geeks") 

        // Applying +:() method 
        val result = q1 +: q2

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
Stack(1, for, geeks)

```

**例 2:**

```scala
// Scala program of mutable stack +:() method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack 
        val q1 = List(1 )

        val q2 = List(11, 12, 13, 14, 15) 

        // Applying ++() method 
        val result = q1.+:(q2) 

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
List(List(11, 12, 13, 14, 15), 1)

```