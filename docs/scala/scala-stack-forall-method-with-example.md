# Scala Stack forall()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-for all-method-with-example/](https://www.geeksforgeeks.org/scala-stack-forall-method-with-example/)

在 Scala `Stack class`中， **forall()** 方法用于检查谓词是否对堆栈的所有元素都成立。

> **方法定义:**定义为 all(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果谓词对堆栈的所有元素都成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of forall() 
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

        // Applying forall method  
        val result = s1.forall(x => {x % 7 == 0}) 

        // Display output
        println("All the elements are divisible by 7: " + result)
    } 
} 
```

**Output:**

```scala
Stack(6, 2, 3, 4, 5)
All the elements are divisible by 7: false

```

**例 2:**

```scala
// Scala program of forall() 
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
        val s1 = Stack(7, 9, 3, 1, 5)  

        // Print the stack
        println(s1)

        // Applying forall method  
        val result = s1.forall(x => {x % 2 == 1}) 

        // Display output
        println("All the elements are odd: " + result)
    } 
} 
```

**Output:**

```scala
Stack(7, 9, 3, 1, 5)
All the elements are odd: true

```