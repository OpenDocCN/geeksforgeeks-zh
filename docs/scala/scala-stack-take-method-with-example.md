# Scala Stack take()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-take-method-with-example/](https://www.geeksforgeeks.org/scala-stack-take-method-with-example/)

在 Scala `Stack class`中， **take()** 方法用于返回由堆栈的前 n 个元素组成的堆栈。

> **方法定义:** def take(n: Int): Stack[A]
> 
> **返回类型:**它返回一个由栈的前‘n’个元素组成的栈。

**示例#1:**

```scala
// Scala program of take() 
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

        // Applying take method  
        val result = s1.take(2)

        // Display output 
        print("Stack containing first two elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Stack containing first two elements: Stack(1, 2)

```

**例 2:**

```scala
// Scala program of take() 
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

        // Applying take method  
        val result = s1.take(3)

        // Display output 
        print("Stack containing first three elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Stack containing first three elements: Stack(1, 2, 3)

```