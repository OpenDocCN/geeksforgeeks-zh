# Scala Stack dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-stack-dropwhile-method-with-example/)

在 Scala `Stack class`中， **dropWhile()** 方法用于从顶部删除满足堆栈中给定谓词的最长前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:Stack[A]
> 
> **返回类型:**在删除满足给定谓词的最长前缀后，它返回一个由元素组成的新堆栈。

**示例#1:**

```scala
// Scala program of dropWhile() 
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

        // Applying dropWhile method  
        val result = s1.dropWhile(x => {x % 2 == 0}) 

        // Displays output  
        print("Stack after using dropWhile() method: " + result)
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
Stack after using dropWhile() method: Stack(3, 4, 5)

```

**例 2:**

```scala
// Scala program of dropWhile() 
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
        val s1 = Stack(1, 7, 2, 3, 4, 5)  

        // Print the stack 
        println(s1)  

        // Applying dropWhile method  
        val result = s1.dropWhile(x => {x % 2 != 0}) 

        // Displays output  
        print("Stack after using dropWhile() method: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 7, 2, 3, 4, 5)
Stack after using dropWhile() method: Stack(2, 3, 4, 5)

```