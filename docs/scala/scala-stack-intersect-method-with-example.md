# Scala Stack intersect()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-intersect-method-with-example/](https://www.geeksforgeeks.org/scala-stack-intersect-method-with-example/)

在 Scala `Stack class`中， **intersect()** 方法用于返回一个新的堆栈，该堆栈由两个给定堆栈中存在的元素组成。

> **方法定义:** def 交集【B】>:A】(即:集合。序列[B]):堆栈[A]
> 
> **返回类型:**它返回一个新的堆栈，该堆栈由存在于两个给定堆栈中的元素组成。

**示例#1:**

```scala
// Scala program of intersect() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 5) 

        val s2 = Stack(1, 13, 2, 17, 6, 15)

        // Print the stack 
        println("Stack_1: " + s1) 

        println("Stack_2: " + s2)

        // Applying intersect method  
        val result = s1.intersect(s2) 

        // Display output 
        print("The elements in both the stacks: ") 

        result.foreach(x => print(x + " "))

    } 
} 
```

**Output:**

```scala
Stack_1: Stack(1, 3, 2, 7, 6, 5)
Stack_2: Stack(1, 13, 2, 17, 6, 15)
The elements in both the stacks: 1 2 6

```

**例 2:**

```scala
// Scala program of intersect() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 5) 

        val s2 = Stack(11, 3, 12, 7, 16, 5)

        // Print the stack 
        println("Stack_1: " + s1) 

        println("Stack_2: " + s2)

        // Applying intersect method  
        val result = s1.intersect(s2) 

        // Display output 
        print("The elements in both the stacks: " + result) 

    } 
} 
```

**Output:**

```scala
Stack_1: Stack(1, 3, 2, 7, 6, 5)
Stack_2: Stack(11, 3, 12, 7, 16, 5)
The elements in both the stacks: Stack(3, 7, 5)

```