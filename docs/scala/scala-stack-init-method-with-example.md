# Scala Stack init()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-init-method-with-example/](https://www.geeksforgeeks.org/scala-stack-init-method-with-example/)

在 Scala `Stack class`中，init()方法用于返回一个新的堆栈，该堆栈由除最后一个元素之外的所有元素组成。

> **方法定义:**定义初始化:堆栈[A]
> 
> **返回类型:**它返回一个新的堆栈，该堆栈由除最后一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of init() 
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

        // Applying init method  
        val result = s1.init 

        // Display output 
        print("Elements of the queue except the last one: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Elements of the queue except the last one: Stack(1, 3, 2, 7, 6)

```

**例 2:**

```scala
// Scala program of init() 
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

        // Applying init method  
        val result = s1.init 

        // Display output 
        print("Elements of the queue except the last one: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 3, 2, 7, 6, 1)
Elements of the queue except the last one: Stack(5, 3, 2, 7, 6)

```