# Scala Stack sum()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-sum-method-with-example/](https://www.geeksforgeeks.org/scala-stack-sum-method-with-example/)

在 Scala `Stack class`中， **sum()** 方法用于返回堆栈中所有元素的总和。

> **方法定义:**定义和:A
> 
> **返回类型:**返回栈中所有元素的和。

**示例#1:**

```scala
// Scala program of sum() 
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
        val s1 = Stack(1, 2, 3, 4, 5) 

        // Print the stack 
        println(s1) 

        // Applying sum method  
        val result = s1.sum

        // Display output 
        print("Sum of all elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Sum of all elements: 15

```

**例 2:**

```scala
// Scala program of sum() 
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

        // Applying sum method  
        val result = s1.sum

        // Display output 
        print("Sum of all elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1)
Sum of all elements: 28

```