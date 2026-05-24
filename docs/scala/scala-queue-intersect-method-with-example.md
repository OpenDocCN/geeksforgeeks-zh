# Scala Queue intersect()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-queue-intersect-method-with-example/](https://www.geeksforgeeks.org/scala-queue-intersect-method-with-example/)

**intersect()** 方法用于返回一个新的队列，该队列由存在于两个给定队列中的元素组成。

> **方法定义:** def 交集【B】>:A】(即:集合。序列[B]):队列[A]
> 
> **返回类型:**它返回一个新的队列，该队列由存在于两个给定队列中的元素组成。

**示例#1:**

```scala
// Scala program of intersect() 
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

        val q2 = Queue(1, 13, 2, 17, 6, 15) 

        // Print the queues
        println("Queue_1: " + q1)

        println("Queue_2: " + q2)

        // Applying intersect method 
        val result = q1.intersect(q2)

        // Display output
        print("The elements in both the queues: ")

        result.foreach(x => print(x + " "))

    } 
} 
```

**Output:**

```scala
Queue_1: Queue(1, 3, 2, 7, 6, 5)
Queue_2: Queue(1, 13, 2, 17, 6, 15)
The elements in both the queues: 1 2 6

```

**例 2:**

```scala
// Scala program of intersect() 
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

        val q2 = Queue(11, 3, 12, 7, 16, 5) 

        // Print the queues
        println("Queue_1: " + q1)

        println("Queue_2: " + q2)

        // Applying intersect method 
        val result = q1.intersect(q2)

        // Display output
        print("The elements in both the queues: " + result)

    } 
} 
```

**Output:**

```scala
Queue_1: Queue(1, 3, 2, 7, 6, 5)
Queue_2: Queue(11, 3, 12, 7, 16, 5)
The elements in both the queues: Queue(3, 7, 5)

```