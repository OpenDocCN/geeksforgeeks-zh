# Scala 栈 splitAt()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-splitat-method-with-example/](https://www.geeksforgeeks.org/scala-stack-splitat-method-with-example/)

在 Scala `Stack class`中， **splitAt()** 方法用于在指定位置将给定堆栈拆分为一对前缀/后缀堆栈。

> **方法定义:** def splitAt(n: Int):(堆栈[A]，堆栈[A])
> 
> **返回类型:**它返回一对堆栈，由这个堆栈的前 n 个元素和其他元素组成。

**示例#1:**

```scala
// Scala program of splitAt() 
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
        val s1 = Stack(5, 2, 13, 7, 1) 

        // Print the stack 
        println(s1) 

        // Applying splitAt method  
        val result = s1.splitAt(2)

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1)
(Stack(5, 2), Stack(13, 7, 1))

```

**例 2:**

```scala
// Scala program of splitAt() 
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
        val s1 = Stack(5, 2, 13, 7, 1) 

        // Print the stack 
        println(s1) 

        // Applying splitAt method  
        val result = s1.splitAt(3)

        // Display output 
        print(result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1)
(Stack(5, 2, 13), Stack(7, 1))

```