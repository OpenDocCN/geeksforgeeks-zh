# Scala Stack 反向()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-reverse-method-with-example/](https://www.geeksforgeeks.org/scala-stack-reverse-method-with-example/)

在 Scala `Stack class`中， **reverse()** 方法用于以相反的顺序返回堆栈。

> **方法定义:** def 反转:堆叠[A]
> 
> **返回类型:**以相反的顺序返回堆栈。

**示例#1:**

```scala
// Scala program of reverse() 
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
        val s1 = Stack(1, 2, 3, 4, 5, 6) 

        // Print the stack 
        println(s1) 

        // Applying reverse method  
        val result = s1.reverse

        // Display output 
        print("Reversed stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5, 6)
Reversed stack: Stack(6, 5, 4, 3, 2, 1)

```

**例 2:**

```scala
// Scala program of reverse() 
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

        // Applying reverse method  
        val result = s1.reverse

        // Display output 
        print("Reversed stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1, 3)
Reversed stack: Stack(3, 1, 7, 13, 2, 5)

```