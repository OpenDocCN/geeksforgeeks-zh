# Scala Queue takeRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-queue-takeright-method-with-example/)

**takeRight()** 方法用于返回由队列的最后 n 个元素组成的队列。

> **方法定义:**定义接受者(n: Int):队列[A]
> 
> **返回类型:**它返回一个由队列的最后‘n’个元素组成的队列。

**示例#1:**

```scala
// Scala program of takeRight() 
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
        val q1 = Queue(5, 2, 13, 7, 1) 

        // Print the queue
        println(q1)

        // Applying takeRight method 
        val result = q1.takeRight(2)

        // Display output
        print("Queue containing last two elements: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Queue containing last two elements: Queue(7, 1)

```

**例 2:**

```scala
// Scala program of takeRight() 
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
        val q1 = Queue(5, 2, 13, 7, 1) 

        // Print the queue
        println(q1)

        // Applying takeRight method 
        val result = q1.takeRight(3)

        // Display output
        print("Queue containing last three elements: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Queue containing last three elements: Queue(13, 7, 1)

```