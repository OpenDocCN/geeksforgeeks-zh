# Scala Stack diff()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-diff-method-with-example/](https://www.geeksforgeeks.org/scala-stack-diff-method-with-example/)

在 Scala `Stack class`中， **diff()** 方法用于查找两个堆栈之间的差异。它从另一个堆栈中删除一个堆栈中的元素。

> **方法定义:**def diff【B】T2:A】(即:集合。序列[B]):堆栈[A]
> 
> **返回类型:**返回一个新的栈，由两个栈差后的元素组成。

**示例#1:**

```scala
// Scala program of diff() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stacks  
        val s1 = Stack(1, 2, 3, 4, 5)  

        val s2 = Stack(3, 4, 5)  

        // Print the stack 
        println("Stack_1: " + s1) 

        println("Stack_2: " + s2) 

        // Applying diff method  
        val result = s1.diff(s2)  

        // Displays output  
        print("(Stack_1 - Stack_2): " + result)
    } 
} 
```

**Output:**

```scala
Stack_1: Stack(1, 2, 3, 4, 5)
Stack_2: Stack(3, 4, 5)
(Stack_1 - Stack_2): Stack(1, 2)

```

**例 2:**

```scala
// Scala program of diff() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stacks  
        val s1 = Stack(1, 2, 3, 4, 5)  

        val s2 = Stack(3, 4, 5, 6, 7, 8)  

        // Print the stack 
        println("Stack_1: " + s1) 

        println("Stack_2: " + s2) 

        // Applying diff method  
        val result = s2.diff(s1)  

        // Displays output  
        print("(Stack_2 - Stack_1): " + result)
    } 
} 
```

**Output:**

```scala
Stack_1: Stack(1, 2, 3, 4, 5)
Stack_2: Stack(3, 4, 5, 6, 7, 8)
(Stack_2 - Stack_1): Stack(6, 7, 8)

```