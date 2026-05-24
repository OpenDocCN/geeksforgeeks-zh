# Scala Queue take()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-take-method-with-example/](https://www.geeksforgeeks.org/scala-queue-take-method-with-example/)

**take()** 方法用于返回由队列的前‘n’个元素组成的队列。

> **方法定义:** def take(n: Int):队列[A]
> 
> **返回类型:**它返回一个由队列的前‘n’个元素组成的队列。

**示例#1:**

```scala
// Scala program of take() 
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

        // Applying take method 
        val result = q1.take(2)

        // Display output
        print("Queue containing first two elements: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Queue containing first two elements: Queue(5, 2)

```

**例 2:**

```scala
// Scala program of take() 
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

        // Applying take method 
        val result = q1.take(3)

        // Display output
        print("Queue containing first three elements: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 2, 13, 7, 1)
Queue containing first three elements: Queue(5, 2, 13)

```