# Scala Stack drop()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-drop-method-with-example/](https://www.geeksforgeeks.org/scala-stack-drop-method-with-example/)

在 Scala `Stack class`中， **drop()** 方法用于从堆栈顶部删除前 n 个元素。

> **方法定义:** def drop(n: Int): Stack[A]
> 
> **返回类型:**它返回一个新的堆栈，除了给定堆栈顶部的前 n 个元素之外，所有元素都在这个堆栈中。

**示例#1:**

```scala
// Scala program of drop() 
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

        // Applying drop method  
        val result = s1.drop(2) 

        // Displays output  
        print("Stack after drop(2) method: " + result)
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
Stack after drop(2) method: Stack(3, 4, 5)

```

**例 2:**

```scala
// Scala program of drop() 
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

        // Applying drop method  
        val result = s1.drop(3) 

        // Displays output  
        print("Stack after drop(3) method: " + result)
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
Stack after drop(3) method: Stack(4, 5)

```