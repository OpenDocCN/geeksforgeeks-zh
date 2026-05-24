# Scala Queue tail()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-tail-method-with-example/](https://www.geeksforgeeks.org/scala-queue-tail-method-with-example/)

**tail()** 方法用于返回一个新队列，该队列由除第一个元素之外的所有元素组成。

> **方法定义:**定义尾部:队列【A】
> 
> **返回类型:**它返回一个新的队列，该队列由除第一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of tail() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queues 
        val q1 = Queue(1, 3, 2, 7, 6, 5) 

        // Print the queue
        println(q1)

        // Applying tail method 
        val result = q1.tail

        // Display output
        print("Tail of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(1, 3, 2, 7, 6, 5)
Tail of the queue: Queue(3, 2, 7, 6, 5)

```

**例 2:**

```scala
// Scala program of tail() 
// method 

// Import Queue  
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating queues 
        val q1 = Queue(5, 3, 2, 7, 6, 1) 

        // Print the queue
        println(q1)

        // Applying tail method 
        val result = q1.tail

        // Display output
        print("Tail of the queue: " + result)

    } 
} 
```

**Output:**

```scala
Queue(5, 3, 2, 7, 6, 1)
Tail of the queue: Queue(3, 2, 7, 6, 1)

```