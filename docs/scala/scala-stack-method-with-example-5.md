# Scala Stack ++:()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-method-with-example-5/](https://www.geeksforgeeks.org/scala-stack-method-with-example-5/)

在 Scala 中，Scala . collection . mutatable 实现了堆栈数据结构。++:方法类似于堆栈中的++方法，它给出了一个新的堆栈，其元素来自左边的操作数，后跟右边的操作数。但不同的是，在++:()中，右操作数决定了结果集合的类型，而不是左操作数。

> **方法定义–**def++:【B>:A，That】(That:集合。可穿越的
> 
> **返回–**一个新的堆栈，它包含该堆栈的所有元素，后跟所有可遍历的元素。

**示例#1:**

```scala
// Scala program of mutable stack ++:() method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack 
        val q1 = Stack(1, 2, 3, 4, 5) 

        val q2 = Stack(11, 12, 13, 14, 15) 

        // Applying ++() method 
        val result = q1.++:(q2) 

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
Stack(11, 12, 13, 14, 15, 1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of mutable stack ++() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack 
        val q1 = List(1, 2, 3)

        val q2 = Stack("for", "geeks") 

        // Applying ++() method 
        val result = q1 ++: q2

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, for, geeks)

```