# Scala Stack tail()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-tail-method-with-example/](https://www.geeksforgeeks.org/scala-stack-tail-method-with-example/)

在 Scala `Stack class`中， **tail()** 方法用于返回一个新的堆栈，该堆栈由除第一个元素之外的所有元素组成。

> **方法定义:**定义尾部:堆栈[A]
> 
> **返回类型:**它返回一个新的堆栈，该堆栈由除第一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of tail() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 5) 

        // Print the stack 
        println(s1) 

        // Applying tail method  
        val result = s1.tail 

        // Display output 
        print("Elements of the queue except the first one: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Elements of the queue except the first one: Stack(3, 2, 7, 6, 5)

```

**例 2:**

```scala
// Scala program of tail() 
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
        val s1 = Stack(5, 3, 2, 7, 6, 1) 

        // Print the stack 
        println(s1) 

        // Applying tail method  
        val result = s1.tail 

        // Display output 
        print("Elements of the queue except the first one: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 3, 2, 7, 6, 1)
Elements of the queue except the first one: Stack(3, 2, 7, 6, 1)

```