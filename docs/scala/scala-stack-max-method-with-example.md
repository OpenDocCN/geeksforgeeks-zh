# Scala Stack max()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-max-method-with-example/](https://www.geeksforgeeks.org/scala-stack-max-method-with-example/)

在 Scala `Stack class`中， **max()** 方法用于返回堆栈中最大的方法。

> **方法定义:** def 最大值:A
> 
> **返回类型:**返回栈中最大的元素。

**示例#1:**

```scala
// Scala program of max() 
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

        // Applying max method  
        val result = s1.max

        // Display output 
        print("The largest element of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 3, 2, 7, 6, 1)
The largest element of the stack: 7

```

**例 2:**

```scala
// Scala program of max() 
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
        val s1 = Stack(15, 13, 12, 7, 6, 11) 

        // Print the stack 
        println(s1) 

        // Applying max method  
        val result = s1.max

        // Display output 
        print("The largest element of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(15, 13, 12, 7, 6, 11)
The largest element of the stack: 15

```