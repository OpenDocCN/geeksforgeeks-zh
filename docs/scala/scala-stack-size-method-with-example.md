# Scala Stack size()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-size-method-with-example/](https://www.geeksforgeeks.org/scala-stack-size-method-with-example/)

在 Scala `Stack class`中， **size()** 方法用于返回堆栈中存在的元素数量。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回堆栈中存在的元素数量。

**示例#1:**

```scala
// Scala program of size() 
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
        val s1 = Stack(1, 2, 3, 4) 

        // Print the stack 
        println(s1) 

        // Applying size method  
        val result = s1.size

        // Display output 
        print("Size of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4)
Size of the stack: 4

```

**例 2:**

```scala
// Scala program of size() 
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
        val s1 = Stack("a", "e", "i", "o", "u") 

        // Print the stack 
        println(s1) 

        // Applying size method  
        val result = s1.size

        // Display output 
        print("Size of the stack: " + result) 

    } 
} 
```

**Output:**

```scala
Stack(a, e, i, o, u)
Size of the stack: 5

```