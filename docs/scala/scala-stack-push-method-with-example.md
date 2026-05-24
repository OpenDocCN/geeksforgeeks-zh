# Scala Stack push()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-push-method-with-example/](https://www.geeksforgeeks.org/scala-stack-push-method-with-example/)

在 Scala `Stack class`中， **push()** 方法用于在堆栈顶部添加元素。

> **方法定义:**def push(elem:A):stack . this . type
> 
> **返回类型:**在栈顶增加一个元素。

**示例#1:**

```scala
// Scala program of push() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a stack
        var s = Stack[Int]() 

        // Applying push method
        s.push(1)
        s.push(2) 
        s.push(3) 
        s.push(4)

        // Print the Stack
        println(s) 

    } 
} 
```

**Output:**

```scala
Stack(4, 3, 2, 1)

```

**例 2:**

```scala
// Scala program of push() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a stack
        var s = Stack[String]() 

        // Applying push method
        s.push("C++")
        s.push("Java") 
        s.push("Python") 
        s.push("Scala")

        // Print the Stack
        println(s) 

    } 
} 
```

**Output:**

```scala
Stack(Scala, Python, Java, C++)

```