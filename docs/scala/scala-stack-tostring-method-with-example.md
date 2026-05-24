# Scala Stack toString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-stack-tostring-method-with-example/)

在 Scala `Stack class`中， **toString()** 方法用于返回堆栈对象的字符串表示。

> **方法定义:** def toString(): String
> 
> **返回类型:**返回堆栈对象的字符串表示形式。

**示例#1:**

```scala
// Scala program of toString() 
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

        // Applying toString method  
        val result = s1.toString

        // Display output 
        print("String representation of the stack object: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
String representation of the stack object: Stack(1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of toString() 
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
        val s1 = Stack(5, 2, 13, 7, 1, 3) 

        // Print the stack 
        println(s1) 

        // Applying toString method  
        val result = s1.toString

        // Display output 
        print("String representation of the stack object: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1, 3)
String representation of the stack object: Stack(5, 2, 13, 7, 1, 3)

```