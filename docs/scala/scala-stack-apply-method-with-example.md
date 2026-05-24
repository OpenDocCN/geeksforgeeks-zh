# Scala 堆栈应用()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-apply-method-with-example/](https://www.geeksforgeeks.org/scala-stack-apply-method-with-example/)

在 Scala `Stack class`中， **apply()** 方法用于返回堆栈中给定位置的元素。栈顶对应 *0 <sup>th</sup>* 位置的元素，依此类推。

> **方法定义:**定义应用(idx: Int):答
> 
> **返回类型:**返回堆栈中给定位置的元素。

**示例#1:**

```scala
// Scala program of apply() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a stack
        val s1 = Stack(1, 2, 3, 4, 5) 

        // Print the stack
        println(s1)

        // Applying apply method    
        val result = s1.apply(0)

        // Display output
        println("Element at 0th position: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Element at 0th position: 1

```

**例 2:**

```scala
// Scala program of apply() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a stack
        val s1 = Stack("C++", "Java", "Python", "Scala") 

        // Print the stack
        println(s1)

        // Applying apply method    
        val result = s1.apply(2)

        // Display output
        println("Element at 2nd position: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(C++, Java, Python, Scala)
Element at 2nd position: Python

```