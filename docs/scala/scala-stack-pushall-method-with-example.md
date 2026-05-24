# Scala Stack pushAll()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-push all-method-with-example/](https://www.geeksforgeeks.org/scala-stack-pushall-method-with-example/)

在 Scala `Stack class`中，**Pusholl()**方法用于将集合中的元素添加到堆栈中。

> **方法定义:**定义 pusholl(elems:iterable once[A]):stack . this . type
> 
> **返回类型:**它返回一个包含给定集合所有元素的堆栈。

**示例#1:**

```scala
// Scala program of pushAll() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack
        var s1 = Stack[String]()

        // Creating a set
        var s2 = Set("C++", "Java", "Python", "Scala") 

        // Print the set
        println(s2)

        // Applying pushAll method    
        s1.pushAll(s2)

        // Print the stack
        println(s1) 

    } 
} 
```

**Output:**

```scala
Set(C++, Java, Python, Scala)
Stack(Scala, Python, Java, C++)

```

**例 2:**

```scala
// Scala program of pushAll() 
// method 

import scala.collection.mutable.Stack 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a stack
        var s1 = Stack[String]()

        // Creating another stack
        var s2 = Stack("C++", "Java", "Python", "Scala") 

        // Print the stack
        println(s2)

        // Applying pushAll method    
        s1.pushAll(s2)

        // Print the stack
        println(s1) 

    } 
} 
```

**Output:**

```scala
Stack(C++, Java, Python, Scala)
Stack(Scala, Python, Java, C++)

```