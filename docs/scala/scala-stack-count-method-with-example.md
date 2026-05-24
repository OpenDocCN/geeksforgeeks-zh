# Scala Stack count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-count-method-with-example/](https://www.geeksforgeeks.org/scala-stack-count-method-with-example/)

在 Scala `Stack class`中， **count()** 方法用于计算堆栈中满足给定谓词的元素数量。

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> **返回类型:**它返回堆栈中满足给定谓词的元素数量的计数。

**示例#1:**

```scala
// Scala program of count() 
// method 

// Import Stack 
import scala.collection.mutable._

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

        // Applying count method 
        val result = s1.count(z => true) 

        // Displays output 
        print("Number of element in stack: " + result) 
    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Number of element in stack: 5

```

**例 2:**

```scala
// Scala program of count() 
// method 

// Import Stack 
import scala.collection.mutable._

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

        // Applying count method 
        val result = s1.count(z => {z % 2 == 0}) 

        // Displays output 
        print("Number of element in stack divisible by 2: " + result) 
    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5)
Number of element in stack divisible by 2: 2

```