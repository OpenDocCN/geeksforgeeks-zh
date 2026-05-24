# Scala Stack exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-exists-method-with-example/](https://www.geeksforgeeks.org/scala-stack-exists-method-with-example/)

在 Scala `Stack class`中， **exists()** 方法用于检查谓词是否适用于堆栈的任何元素。

> **方法定义:** def 存在(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果谓词对堆栈的任何元素都成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of exists() 
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

        // Applying exists method  
        val result = s1.exists(x => {x % 7 == 0}) 

        // Display output
        println("Element divisible by 7 exists: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Element divisible by 7 exists: true

```

**例 2:**

```scala
// Scala program of exists() 
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

        // Applying exists method  
        val result = s1.exists(x => {x == 10}) 

        // Display output
        println("Element 10 exists: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Element 10 exists: false

```