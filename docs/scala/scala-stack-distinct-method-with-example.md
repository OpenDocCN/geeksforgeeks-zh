# Scala Stack distinct()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-distinct-method-with-example/](https://www.geeksforgeeks.org/scala-stack-distinct-method-with-example/)

在 Scala `Stack class`中， **distinct()** 方法用于从给定的堆栈中删除重复的元素。

> **方法定义:** def distinct: Stack[A]
> 
> **返回类型:**它返回一个只有不同元素的新堆栈。

**示例#1:**

```scala
// Scala program of distinct() 
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
        val s1 = Stack(1, 3, 2, 1, 2, 1, 3, 2, 3, 3) 

        // Print the stack
        println(s1) 

        // Applying distinct() method  
        val result = s1.distinct

        // Display output 
        print("Stack with distinct elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 1, 2, 1, 3, 2, 3, 3)
Stack with distinct elements: Stack(1, 3, 2)

```

**例 2:**

```scala
// Scala program of distinct() 
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
        val s1 = Stack("g", "e", "e", "k", "s", "f", "o", "r", "g", "e", "e", "k", "s") 

        // Print the stack
        println(s1) 

        // Applying distinct() method  
        val result = s1.distinct

        // Display output 
        print("Stack with distinct elements: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(g, e, e, k, s, f, o, r, g, e, e, k, s)
Stack with distinct elements: Stack(g, e, k, s, f, o, r)

```