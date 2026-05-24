# Scala Stack filter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-filter-method-with-example/](https://www.geeksforgeeks.org/scala-stack-filter-method-with-example/)

在 Scala `Stack class`中， **filter()** 方法用于返回一个新的堆栈，该堆栈由满足给定谓词的所有元素组成。

> **方法定义:** def 过滤器(pred: (A) = >布尔型:堆栈[A]
> 
> **返回类型:**它返回一个新的堆栈，该堆栈由满足给定谓词的所有元素组成。

**示例#1:**

```scala
// Scala program of filter() 
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

        // Applying filter method  
        val result = s1.filter(x => {x % 2 == 1}) 

        // Display output
        println("Odd elements: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Odd elements: Stack(1, 3, 7, 5)

```

**例 2:**

```scala
// Scala program of filter() 
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

        // Applying filter method  
        val result = s1.filter(x => {x % 3 == 0}) 

        // Display output
        println("Elements divisible by 3: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Elements divisible by 3: Stack(3, 6)

```