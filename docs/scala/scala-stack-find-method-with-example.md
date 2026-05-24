# Scala Stack find()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-find-method-with-example/](https://www.geeksforgeeks.org/scala-stack-find-method-with-example/)

在 Scala `Stack class`中， **find()** 方法用于返回满足堆栈中给定谓词的元素。

> **方法定义:** def find(p: (A) = > Boolean:选项【A】
> 
> **返回类型:**返回满足给定谓词的第一个元素(如果存在)，否则返回无。

**示例#1:**

```scala
// Scala program of find() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 5)  

        // Print the stack
        println(s1)

        // Applying find method  
        val result = s1.find(x => {x % 7 == 0}) 

        // Display output
        println("Element divisible by 7: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Element divisible by 7: Some(7)

```

**例 2:**

```scala
// Scala program of find() 
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
        val s1 = Stack(1, 3, 2, 7, 6, 5)  

        // Print the stack
        println(s1)

        // Applying find method  
        val result = s1.find(x => {x % 10 == 0}) 

        // Display output
        println("Element divisible by 10: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Element divisible by 10: None

```