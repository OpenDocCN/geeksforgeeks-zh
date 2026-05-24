# Scala Queue toMap()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-tomap-method-with-example/](https://www.geeksforgeeks.org/scala-queue-tomap-method-with-example/)

**toMap()** 方法用于返回由队列的所有元素组成的映射。

> **方法定义:** def toMap[T，U]: Map[T，U]
> 
> **返回类型:**它返回一个由队列所有元素组成的映射。

**示例#1:**

```scala
// Scala program of toMap() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a queue 
        val q1 = Queue((1, 2), (3, 4), (5, 6)) 

        // Print the queue
        println(q1)

        // Applying toMap method 
        val result = q1.toMap

        // Display output
        print("Elements in the Map: " + result)

    } 
} 
```

**Output:**

```scala
Queue((1, 2), (3, 4), (5, 6))
Elements in the Map: Map(1 -> 2, 3 -> 4, 5 -> 6)

```

**例 2:**

```scala
// Scala program of toMap() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a queue 
        val q1 = Queue((5, 2), (13, 7), (1, 3)) 

        // Print the queue
        println(q1)

        // Applying toMap method 
        val result = q1.toMap

        // Display output
        print("Elements in the Map: " + result)

    } 
} 
```

**Output:**

```scala
Queue((5, 2), (13, 7), (1, 3))
Elements in the Map: Map(5 -> 2, 13 -> 7, 1 -> 3)

```