# Scala Stack 克隆()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-clone-method-with-example/](https://www.geeksforgeeks.org/scala-stack-clone-method-with-example/)

在 Scala `Stack class`中，**克隆()**方法用于创建给定堆栈的副本。

> **方法定义:** def 克隆():堆栈[A]
> 
> **返回类型:**它返回一个新的堆栈，它是给定堆栈的副本。

**示例#1:**

```scala
// Scala program of clone() 
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

        // Applying clone method  
        val result = s1.clone  

        // Displays output  
        print("Clone of the stack: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Clone of the stack: Stack(1, 2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of clone() 
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
        val s1 = Stack(3, 4, 5, 6, 7, 8)  

        // Print the stack 
        println(s1) 

        // Applying clone method  
        val result = s1.clone  

        // Displays output  
        print("Clone of the stack: " + result)
    } 
} 
```

**Output:**

```scala
Stack(3, 4, 5, 6, 7, 8)
Clone of the stack: Stack(3, 4, 5, 6, 7, 8)

```