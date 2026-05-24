# Scala Stack pop()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-pop-method-with-example/](https://www.geeksforgeeks.org/scala-stack-pop-method-with-example/)

在 Scala `Stack class`中， **pop()** 方法用于移除并返回堆栈顶部的元素。

> **方法定义:** def pop(): A
> 
> **返回类型:**移除并返回堆栈顶部的元素。

**示例#1:**

```scala
// Scala program of pop() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a stack
        var s = Stack("C++", "Java", "Python", "Scala") 

        // Print the stack
        println(s)

        // Print the top of the stack
        println("Top of the stack: " + s.top)

        // Applying pop method    
        val result = s.pop

        // Print the popped element
        println("Popped element: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(C++, Java, Python, Scala)
Top of the stack: C++
Popped element: C++

```

**例 2:**

```scala
// Scala program of pop() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a stack
        var s = Stack(1, 2, 3, 4) 

        // Print the stack
        println(s)

        // Print the top of the stack
        println("Top of the stack: " + s.top)

        // Applying pop method    
        val result = s.pop

        // Print the popped element
        println("Popped element: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Top of the stack: 1
Popped element: 1

```