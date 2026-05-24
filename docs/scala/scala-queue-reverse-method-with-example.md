# Scala Queue 反向()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-reverse-method-with-example/](https://www.geeksforgeeks.org/scala-queue-reverse-method-with-example/)

**reverse()** 方法用于以相反的顺序返回队列。

> **方法定义:**定义反转:队列【A】
> 
> **返回类型:**返回一个顺序相反的队列。

**示例#1:**

```scala
// Scala program of reverse() 
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
        val q1 = Queue(1, 2, 3, 4, 5) 

        // Print the queue
        println(q1)

        // Applying reverse method 
        val result = q1.reverse

        // Display output
        print("Reversed queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 2, 3, 4, 5)
Reversed queue: Queue(5, 4, 3, 2, 1)

```

**例 2:**

```scala
// Scala program of reverse() 
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
        val q1 = Queue(5, 2, 13, 7, 1, 3) 

        // Print the queue
        println(q1)

        // Applying reverse method 
        val result = q1.reverse

        // Display output
        print("Reversed queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1, 3)
Reversed queue: Queue(3, 1, 7, 13, 2, 5)

```