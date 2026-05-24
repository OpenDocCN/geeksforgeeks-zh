# Scala Stack top()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-top-method-with-example/](https://www.geeksforgeeks.org/scala-stack-top-method-with-example/)

在 Scala `Stack class`中， **top()** 方法用于返回堆栈的顶部元素。

> **方法定义:**定义顶部:A
> 
> **返回类型:**返回栈顶元素。

**示例#1:**

```scala
// Scala program of top() 
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

        // Applying top method  
        val result = s1.top 

        // Display output 
        print("Top element of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Top element of the stack: 1

```

**例 2:**

```scala
// Scala program of top() 
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

        // Applying top method  
        val result = s1.top 

        // Display output 
        print("Top element of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 3, 2, 7, 6, 1)
Top element of the stack: 5

```