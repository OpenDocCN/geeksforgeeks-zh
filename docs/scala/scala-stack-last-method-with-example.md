# Scala Stack last()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-last-method-with-example/](https://www.geeksforgeeks.org/scala-stack-last-method-with-example/)

在 Scala `Stack class`中， **last()** 方法用于返回堆栈的最后一个元素。

> **方法定义:**定义最后:答
> 
> **返回类型:**返回栈的最后一个元素。

**示例#1:**

```scala
// Scala program of last() 
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

        // Applying last method  
        val result = s1.last

        // Display output 
        print("The last element of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
The last element of the stack: 5

```

**例 2:**

```scala
// Scala program of last() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 13) 

        // Print the stack 
        println(s1) 

        // Applying last method  
        val result = s1.last

        // Display output 
        print("The last element of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 13)
The last element of the stack: 13

```