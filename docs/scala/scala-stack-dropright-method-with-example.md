# Scala Stack dropRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-stack-dropright-method-with-example/)

在 Scala `Stack class`中， **dropRight()** 方法用于删除堆栈的最后 n 个元素。

> **方法定义:** def dropRight(n: Int):堆栈[A]
> 
> **返回类型:**它返回一个新的堆栈，该堆栈由除最后‘n’个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of dropRight() 
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
        val s1 = Stack(6, 2, 3, 4, 5)  

        // Print the stack 
        println(s1)  

        // Applying dropRight method  
        val result = s1.dropRight(2) 

        // Displays output  
        print("Stack after dropRight(2) method: " + result)
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
Stack after dropRight(2) method: Stack(6, 2, 3)

```

**例 2:**

```scala
// Scala program of dropRight() 
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
        val s1 = Stack(6, 2, 3, 4, 5)  

        // Print the stack 
        println(s1)  

        // Applying dropRight method  
        val result = s1.dropRight(3) 

        // Displays output  
        print("Stack after dropRight(3) method: " + result)
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
Stack after dropRight(3) method: Stack(6, 2)

```