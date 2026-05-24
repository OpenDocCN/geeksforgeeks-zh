# Scala Stack equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-equals-method-with-example/](https://www.geeksforgeeks.org/scala-stack-equals-method-with-example/)

在 Scala `Stack class`中，**等于()**方法用于检查两个堆栈是否由相同顺序的相同元素组成。

> **方法定义:** def 等于(o: Any): Boolean
> 
> **返回类型:**如果两个栈相同则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of equals() 
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

        val s2 = Stack(1, 3, 2, 7, 6, 5)

        // Print the stack 
        println("Stack_1: " + s1) 

        println("Stack_2: " + s2)

        // Applying equals method  
        val result = s1.equals(s2) 

        // Display output
        println("Stack_1 == Stack_2: " + result)
    } 
} 
```

**输出:**

```scala
Stack_1: Stack(1, 3, 2, 7, 6, 5)
Stack_2: Stack(1, 3, 2, 7, 6, 5)
Stack_1 == Stack_2: true

```