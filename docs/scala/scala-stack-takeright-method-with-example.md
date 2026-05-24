# Scala Stack takeRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-stack-takeright-method-with-example/)

在 Scala `Stack class`中， **takeRight()** 方法被用来返回一个由栈的最后 n 个元素组成的栈。

> **方法定义:**def taker right(n:Int):Stack[A]
> 
> **返回类型:**它返回一个由栈的最后‘n’个元素组成的栈。

**示例#1:**

```scala
// Scala program of takeRight() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stack
        val s1 = Stack(1, 2, 3, 4) 

        // Print the stack 
        println(s1) 

        // Applying takeRight method  
        val result = s1.takeRight(2)

        // Display output 
        print("Stack containing last two elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Stack containing last two elements: Stack(3, 4)

```

**例 2:**

```scala
// Scala program of takeRight() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stack
        val s1 = Stack(1, 2, 3, 4) 

        // Print the stack 
        println(s1) 

        // Applying takeRight method  
        val result = s1.takeRight(3)

        // Display output 
        print("Stack containing last three elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Stack containing last three elements: Stack(2, 3, 4)

```