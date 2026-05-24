# Scala 栈包含()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-contains-method-with-example/](https://www.geeksforgeeks.org/scala-stack-contains-method-with-example/)

在 Scala `Stack class`中， **contains()** 方法用于检查元素是否存在于 not 堆栈中。

> **方法定义:** def 包含(elem: A):布尔值
> 
> **返回类型:**如果元素存在于堆栈中，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of contains() 
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

        // Applying contains method    
        val result = s1.contains(10)

        // Display output
        println("Stack contains element 10: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Stack contains element 10: false

```

**例 2:**

```scala
// Scala program of contains() 
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

        // Applying contains method    
        val result = s1.contains("Scala")

        // Display output
        println("Stack contains element Scala: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(C++, Java, Python, Scala)
Stack contains element Scala: true

```