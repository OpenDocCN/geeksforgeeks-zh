# Scala Stack toMap()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-tomap-method-with-example/](https://www.geeksforgeeks.org/scala-stack-tomap-method-with-example/)

在 Scala `Stack class`中， **toMap()** 方法被用来返回一个由栈的所有元素组成的映射。

> **方法定义:** def toMap[T，U]: Map[T，U]
> 
> **返回类型:**它返回一个由栈的所有元素组成的映射。

**示例#1:**

```scala
// Scala program of toMap() 
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
        val s1 = Stack((1, 2), (3, 4), (5, 6)) 

        // Print the stack 
        println(s1) 

        // Applying toMap method  
        val result = s1.toMap

        // Display output 
        print("Elements in the map: " + result) 

    } 
} 
```

**Output:**

```scala
Stack((1, 2), (3, 4), (5, 6))
Elements in the map: Map(1 -> 2, 3 -> 4, 5 -> 6)

```

**例 2:**

```scala
// Scala program of toMap() 
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
        val s1 = Stack((5, 2), (13, 7), (1, 3)) 

        // Print the stack 
        println(s1) 

        // Applying toMap method  
        val result = s1.toMap

        // Display output 
        print("Elements in the map: " + result) 

    } 
} 
```

**Output:**

```scala
Stack((5, 2), (13, 7), (1, 3))
Elements in the map: Map(5 -> 2, 13 -> 7, 1 -> 3)

```